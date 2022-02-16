# multidevicenetmikoscript.py
multiple device configuration script in python.
from netmiko import ConnectHandler 
# from getpass import getpass

# password= getpass()

cisco1 = {

         'device_type': 'cisco_ios',
         'host': '10.100.10.101',
         'username': 'admin',
         'password': 'password',
         'port': 22
}

cisco2 = { 'device_type': 'cisco_ios', 
           'host': '10.100.10.102', 
           'username': 'admin', 
           'password': 'password',
           'port': 22
 }
           

device_list = [cisco1,cisco2] 

for device in device_list: print('Connecting to the device :' + device ['host']) 

net_connect = ConnectHandler(**device)

output = net_connect.send_command('show ip interface brief')
print(output)
output = net_connect.send_command('show version')
print(output)
