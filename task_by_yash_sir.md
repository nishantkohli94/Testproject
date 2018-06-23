--
# tasks file for ps_cms_app_deploment

- name: restart the Gunicorn Serveice 
  service: name=gunicorn state=stopped 

- name: remove old Arftifact
  file: state=absent path={{ proj_dir }}/{{ app_dir }}

- name: remove old Arftifact
  file: state=absent path={{ proj_dir }}/{{ venv }}


- name: Installing the dependency
  yum: name={{ item }} state=present
  with_items: 
       - mariadb-libs.x86_64
       - mysql-devel
       - python3-devel.x86_64
       - python-devel.x86_64
       - python-pip
       - python-virtualenv

- name: Creating a directory
  file: path={{ proj_dir }}  state=directory  owner=ec2-user mode=755

#- name: Creting Virtual Environment Directory
#  file: path={{ proj_dir }}/{{ app_dir }} state=directory owner=ec2-user

- name: Copy the Python path
  copy: content="export PYTHONPATH=/data" dest=/etc/environment

- name: Use the python version
  shell: source /etc/environment

- name: Creating the virtual path
  pip: name=gunicorn virtualenv={{ proj_dir }}/{{ venv }}  virtualenv_python=/usr/local/bin/python3.6

- name: Install the gunicorn 
  pip: name=gunicorn  virtualenv={{ proj_dir }}/{{ venv }}

- name: Download Artifact 
  get_url: url="http://nexus.ntuclink.cloud/repository/{{repo}}/{{ package_name }}"  dest=/tmp/ remote_src=yes url_username=admin url_password="admin123"

- name: unarchive the zip file
  unarchive: src="/tmp/{{package_name}}" dest={{ proj_dir }} owner=ec2-user mode=755 remote_src=yes

- name: Setting the ec2-user permission
  file: dest={{ proj_dir }}/{{ app_dir }} owner=ec2-user group=ec2-user  recurse=yes

- name: Installing the requirement.txt
  pip: requirements={{ proj_dir }}/{{ app_dir }}/requirements.txt  virtualenv={{ proj_dir }}/{{ venv }}

- name: Downloading the config.json
  get_url: url=http://nexus.ntuclinc.com/repository/PropertyFiles/cms-ps-prod/config.json dest={{ proj_dir }}/{{ app_dir }} remote_src=yes url_username=admin url_password="admin12345"

- name: collect static files
  django_manage: command=collectstatic   app_path={{ proj_dir }}/{{ app_dir }} virtualenv={{ proj_dir }}/{{ venv }}

- name: Setting the ec2-user permission
  file: dest={{ proj_dir }} owner=ec2-user group=ec2-user  recurse=yes


- name: restart the Gunicorn Serveice 
  service: name=gunicorn state=restarted
