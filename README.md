1.����manager.py������������Ϣ��
host = '172.16.1.162' #Ҫ��¼������
user = 'aaa'          #netconf�û���
password = 'aaa'      #netconf����

ע�⣺�뱣֤h3c�豸����netconf����
����,��h3c������������������Ϣ������μ�press�ֲᡣ
system-view
local-user aaa class manage
password simple aaa
authorization-attribute user-role network-admin work-directory flash:/
service-type https
quit
netconf soap https enable
quit

2.ִ��set_static_route_tableΪ���þ�̬·��
  ִ��delete_static_route_table.pyΪɾ����̬·��

����Ҫ�µ�����д��manager.py���棬netconf�ӿڲ��� doc/Comware V7 StaticRoute NETCONF XML API Configuration Reference

���磬��̬·�ɵ���ϢΪ��
	DestVrfIndex = '0'
	DestTopologyIndex = '0'
	Ipv4Address = '3.3.3.3'
	Ipv4PrefixLength = '24'
	NexthopVrfIndex = '0'
	NexthopIpv4Address = '4.4.4.1'
	IfIndex = '0'
	

3.��ȡ�豸�������ļ�
ִ��get_config_file.py���Ի�ȡ�����ļ�

ע������h3c������������ftp server���ṩftp����
����,��h3c������������������Ϣ������μ�press�ֲᡣ
system-view
local-user aaa  class manage
password simple aaa
authorization-attribute user-role network-admin work-directory flash:/
service-type ftp 
quit
ftp server enable
quit


