OCP Cronjob creation
=======================================

The role *"roles/ocp-cronjob"* provides automated creation of cronjobs. User can add cronjob value in the role variables for creation **Role Variables** section.
This role will create the cronjob and we can monitor the jobs usig oc commands


Requirements
------------

 - Running OCP 4.x cluster.


Role Variables
--------------

| Variable                       | Required | Default                   |Comments                                                                                                                                                                                                                                                                          |
|--------------------------------|----------|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| enable_cronjob        		 | no      | false                     | Flag to be set to true to enable cronjob |   
| cronjob_schedule        		  	 | no      | * * * * *               | can be updated as needed |                                                                                                                                                                                                        |
| cronjob_concurrencyPolicy           | no       | Allow              		| Value can be anything from ["Allow","forbid","replace"]     |
| cronjob_startingDeadlineSeconds     | no       | 200              			| Can be updated as needed    |
| cronjob_suspend             		 | no       | false              		| can be true or false |
| cronjob_successfulJobsHistoryLimit  | no       | 3              			| can be updated as needed     |
| cronjob_failedJobsHistoryLimit      | no       | 2             			| can be updated as needed    |
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Dependencies
------------

 - None


Example Playbook
----------------

    - name: Start cronjob
      hosts: bastion
      roles:
        - ocp-cronjob


Steps to run playbook
----------------------

 - Copy the ocp4-playbooks-extras/examples/inventory to the home/working directory
 - To execute the playbook run the below sample command


Sample Command
---------------

ansible-playbook -i inventory -e @examples/all.yaml ~/ocp4-playbooks-extras/playbooks/ocp-cronjob.yml


License
-------

See LICENCE.txt


Author Information
------------------

Swapnil Bobade (swapnil.bobade@ibm.com)
