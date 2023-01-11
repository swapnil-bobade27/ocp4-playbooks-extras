OCP Pod disruption budget
=======================================

The role *"roles/ocp-pod-disruption-budget"* is an object to define the max disruption that can be caused to a collection of pods.



Requirements
------------

 - Running OCP 4.x cluster.


Role Variables
--------------

| Variable                       | Required | Default                   |Comments                                                                                                                                                                                                                                                                          |
|--------------------------------|----------|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| pdb_enable        		     | no       | false                     | Flag to be set to true to enable pod disruption budget |   
| pdb_minAvailable        		 | no       | 3                         | Number of pods must always be available, even during a disruption |                      
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Dependencies
------------

 - None


Example Playbook
----------------

    - name: Start Pod disruption budget
      hosts: bastion
      roles:
        - ocp-pod-disruption-budget


Steps to run playbook
----------------------

 - Copy the ocp4-playbooks-extras/examples/inventory to the home/working directory
 - To execute the playbook run the below sample command


Sample Command
---------------

ansible-playbook -i inventory -e @examples/all.yaml ~/ocp4-playbooks-extras/playbooks/ocp-pod-disruption-budget.yml


License
-------

See LICENCE.txt


Author Information
------------------

Swapnil Bobade (swapnil.bobade@ibm.com)
