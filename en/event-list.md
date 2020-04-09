## CloudTrail > 수집되는 이벤트 목록

|Event|Event ID|Service|
| --- | --- | --- |
|Create Schedule for Scaling Group|event_id.iaas.autoscale_schedule.create|Default Infrastructure Service|
|Delete Schedule for Scaling Group|event_id.iaas.autoscale_schedule.delete|Default Infrastructure Service|
|Associate Instance Floating IP |event_id.iaas.floating_ip.attach|Default Infrastructure Service|
|Create Floating IP|event_id.iaas.floating_ip.create|Default Infrastructure Service|
|Delete Floating IP|event_id.iaas.floating_ip.delete|Default Infrastructure Service|
|Disassociate Instance Floating IP|event_id.iaas.floating_ip.detach|Default Infrastructure Service|
|Create Image|event_id.iaas.image.create|Default Infrastructure Service|
|Delete Image|event_id.iaas.image.delete|Default Infrastructure Service|
|Change Image Information|event_id.iaas.image.update|Default Infrastructure Service|
|Create Image Sharing|event_id.iaas.image_member.create|Default Infrastructure Service|
|Delete Image Sharing|event_id.iaas.image_member.delete|Default Infrastructure Service|
|Create Instance|event_id.iaas.instance.create|Default Infrastructure Service|
|Delete Instance|event_id.iaas.instance.delete|Default Infrastructure Service|
|Change Instance Information|event_id.iaas.instance.update|Default Infrastructure Service|
|Reboot Instance|event_id.iaas.instance_action.reboot|Default Infrastructure Service|
|Change Instance Type|event_id.iaas.instance_action.resize|Default Infrastructure Service|
|Start Instance|event_id.iaas.instance_action.start|Default Infrastructure Service|
|Close Instance|event_id.iaas.instance_action.stop|Default Infrastructure Service|
|Create Instance Template|event_id.iaas.instance_template.create|Default Infrastructure Service|
|Delete Instance Template|event_id.iaas.instance_template.delete|Default Infrastructure Service|
|Change Instance Template|event_id.iaas.instance_template.update|Default Infrastructure Service|
|Create Instance Interface|event_id.iaas.interface.create|Default Infrastructure Service|
|Delete Instance Interface|event_id.iaas.interface.delete|Default Infrastructure Service|
|Create Internet Gateway|event_id.iaas.internet_gateway.create|Default Infrastructure Service|
|Delete Internet Gateway|event_id.iaas.internet_gateway.delete|Default Infrastructure Service|
|Create Keypair|event_id.iaas.keypair.create|Default Infrastructure Service|
|Delete Keypair|event_id.iaas.keypair.delete|Default Infrastructure Service|
|Create Load Balancer|event_id.iaas.loadbalancer.create|Default Infrastructure Service|
|Delete Load Balancer|event_id.iaas.loadbalancer.delete|Default Infrastructure Service|
|Change Load Balancer Information|event_id.iaas.loadbalancer.update|Default Infrastructure Service|
|Create Load Balancer Listener|event_id.iaas.loadbalancer_listener.create|Default Infrastructure Service|
|Delete Load Balancer Listener|event_id.iaas.loadbalancer_listener.delete|Default Infrastructure Service|
|Change Load Balancer Listener|event_id.iaas.loadbalancer_listener.update|Default Infrastructure Service|
|Attach Load Balancer Instance|event_id.iaas.loadbalancer_member.create|Default Infrastructure Service|
|Detach Load Balancer Instance|event_id.iaas.loadbalancer_member.delete|Default Infrastructure Service|
|Change Status of Load Balancer Instance|event_id.iaas.loadbalancer_member.update|Default Infrastructure Service|
|Create Instance Metadata|event_id.iaas.metadata.create|Default Infrastructure Service|
|Delete Instance Metadata|event_id.iaas.metadata.delete|Default Infrastructure Service|
|Change Instance Metadata|event_id.iaas.metadata.update|Default Infrastructure Service|
|Create VPC Peering|event_id.iaas.peering.create|Default Infrastructure Service|
|Delete VPC Peering|event_id.iaas.peering.delete|Default Infrastructure Service|
|Create Port|event_id.iaas.port.create|Default Infrastructure Service|
|Delete Port|event_id.iaas.port.delete|Default Infrastructure Service|
|Change Port Security Group|event_id.iaas.port.update|Default Infrastructure Service|
|Create Route in Routing Table|event_id.iaas.route.create|Default Infrastructure Service|
|Delete Route in Routing Table|event_id.iaas.route.delete|Default Infrastructure Service|
|Connect Routing Table over Internet Gateway|event_id.iaas.routing_table.attach_gateway|Default Infrastructure Service|
|Create Routing Table|event_id.iaas.routing_table.create|Default Infrastructure Service|
|Delete Routing Table|event_id.iaas.routing_table.delete|Default Infrastructure Service|
|Disconnect Routing Table over Internet Gateway|event_id.iaas.routing_table.detach_gateway|Default Infrastructure Service|
|Set Default Routing Table|event_id.iaas.routing_table.set_as_default|Default Infrastructure Service|
|Change Routing Table|event_id.iaas.routing_table.update|Default Infrastructure Service|
|Create Scaling Group|event_id.iaas.scaling_group.create|Default Infrastructure Service|
|Delete Scaling Group|event_id.iaas.scaling_group.delete|Default Infrastructure Service|
|Change Scaling Group|event_id.iaas.scaling_group.update|Default Infrastructure Service|
|Create Security Group|event_id.iaas.security_group.create|Default Infrastructure Service|
|Delete Security Group|event_id.iaas.security_group.delete|Default Infrastructure Service|
|Change Security Group|event_id.iaas.security_group.update|Default Infrastructure Service|
|Create Security Policy|event_id.iaas.security_group_rule.create|Default Infrastructure Service|
|Delete Security Policy|event_id.iaas.security_group_rule.delete|Default Infrastructure Service|
|Create Block Storage Snapshot|event_id.iaas.snapshot.create|Default Infrastructure Service|
|Delete Block Storage Snapshot|event_id.iaas.snapshot.delete|Default Infrastructure Service|
|Connect Instance Volume|event_id.iaas.volume.attach|Default Infrastructure Service|
|Create Block Storage|event_id.iaas.volume.create|Default Infrastructure Service|
|Delete Block Storage|event_id.iaas.volume.delete|Default Infrastructure Service|
|Disconnect Instance Volume|event_id.iaas.volume.detach|Default Infrastructure Service|
|Change Block Storage Information|event_id.iaas.volume.update|Default Infrastructure Service|
|Create VPC|event_id.iaas.vpc.create|Default Infrastructure Service|
|Delete VPC|event_id.iaas.vpc.delete|Default Infrastructure Service|
|Change VPC Information|event_id.iaas.vpc.update|Default Infrastructure Service|
|Connect Routing Table over VPC Subnet|event_id.iaas.vpc_subnet.attach_routingtable|Default Infrastructure Service|
|Create VPC Subnet|event_id.iaas.vpc_subnet.creat|Default Infrastructure Service|
|Delete VPC Subnet|event_id.iaas.vpc_subnet.delet|Default Infrastructure Service|
|Disconnect Routing Table over VPC Subnet|event_id.iaas.vpc_subnet.detach_routingtable|Default Infrastructure Service|
|Change VPC Subnet|event_id.iaas.vpc_subnet.update|Default Infrastructure Service|
|Query Account|event_id.object_storage.account.look_up|Object Storage|
|Register/Modify Account Metadata|event_id.object_storage.account.metadata.update|Object Storage|
|List Containers|event_id.object_storage.container.look_up|Object Storage|
|Query Containers|event_id.object_storage.container.look_up|Object Storage|
|Create Containers|event_id.object_storage.container.create|Object Storage|
|Delete Containers|event_id.object_storage.container.delete|Object Storage|
|Register/Modify Container Metadata|event_id.object_storage.container.metadata.update|Object Storage|
|List Objects|event_id.object_storage.object.look_up|Object Storage|
|Query Objects|event_id.object_storage.object.look_up|Object Storage|
|Upload objects|event_id.object_storage.object.upload|Object Storage|
|Download objects|event_id.object_storage.object.download|Object Storage|
|Copy objects|event_id.object_storage.object.copy|Object Storage|
|Delete objects|event_id.object_storage.object.delete|Object Storage|
|Register/Modify Object Metadata|event_id.object_storage.object.metadata.update|Object Storage|
|DB 인스턴스 생성|event_id.rds_for_mysql.instance.create|RDS for MySQL|
|DB 인스턴스 삭제|event_id.rds_for_mysql.instance.delete|RDS for MySQL|
|DB 인스턴스 상세 설정 변경|event_id.rds_for_mysql.instance.detail.update|RDS for MySQL|
|DB 인스턴스 관리 정보 변경|event_id.rds_for_mysql.instance.management.update|RDS for MySQL|
|DB 인스턴스 Configuration 변경|event_id.rds_for_mysql.instance.configuration.update|RDS for MySQL|
|DB 인스턴스 백업|event_id.rds_for_mysql.instance_action.backup|RDS for MySQL|
|DB 인스턴스 복원|event_id.rds_for_mysql.instance_action.restore|RDS for MySQL|
|DB 인스턴스 복제|event_id.rds_for_mysql.instance_action.replicate|RDS for MySQL|
|DB 인스턴스 재시작|event_id.rds_for_mysql.instance_action.restart|RDS for MySQL|
|DB 인스턴스 승격|event_id.rds_for_mysql.instance_action.promote|RDS for MySQL|
|DB 인스턴스 스토리지 확장|event_id.rds_for_mysql.instance.volume.extend|RDS for MySQL|
|DB 인스턴스 용량 확보|event_id.rds_for_mysql.instance.volume.secure|RDS for MySQL|
|백업 삭제|event_id.rds_for_mysql.instance.backup.delete|RDS for MySQL|
|알림 생성|event_id.rds_for_mysql.notification.create|RDS for MySQL|
|알림 변경|event_id.rds_for_mysql.notification.update|RDS for MySQL|
|알림 삭제|event_id.rds_for_mysql.notification.delete|RDS for MySQL|
|알림 활성화|event_id.rds_for_mysql.notification.enable|RDS for MySQL|
|알림 비활성화|event_id.rds_for_mysql.notification.disable|RDS for MySQL|
|수신 그룹 생성|event_id.rds_for_mysql.receiver_group.create|RDS for MySQL|
|수신 그룹 변경|event_id.rds_for_mysql.receiver_group.update|RDS for MySQL|
|수신 그룹 삭제|event_id.rds_for_mysql.receiver_group.delete|RDS for MySQL|
|IAM Login|event_id.iam.login|Console|
|Change Authority for IAM Members|event_id.iam.member.role.update|Console|
|Add Organization Domain|event_id.org.domain.add|Console|
|Modify Organization Domain|event_id.org.domain.update|Console|
|Add Organization Member|event_id.org.iam.member.add|Console|
|Send Notification Mail to Organization Members to Change Password|event_id.org.iam.member.send_mail|Console| 
|Modify Organization Member Information|event_id.org.iam.member.update|Console|
|Add Organization Member|event_id.org.member.add|Console|
|Delete Organization Member|event_id.org.member.delete|Console|
|Invite Organization Member|event_id.org.member.invite|Console|
|Cancel Organization Member Invitation|event_id.org.member.invite_cancel|Console|  
|Modify Organization Member|event_id.org.member.update|Console|
|Disable Organization Service|event_id.org.product.disable|Console|
|Enable Organization Service|event_id.org.product.enable|Console|
|Modify Organization Information|event_id.org.update|Console|
|Create Project|event_id.project.create|Console|
|Delete Project|event_id.project.delete|Console|
|Add Project Member|event_id.project.member.add|Console|
|Delete Project Member|event_id.project.member.delete|Console|
|Invite Project Member|event_id.project.member.invite|Console|
|Cancel Project Member Invitation|event_id.project.member.invite_cancel|Console|
|Modify Project Member Authority|event_id.project.member.update|Console|
|Delete Project Member|event_id.project.members.delete|Console|
|Disable Project Service|event_id.project.product.disable|Console|
|Enable Project Service|event_id.project.product.enable|Console|
|Modify Project|event_id.project.update|Console|