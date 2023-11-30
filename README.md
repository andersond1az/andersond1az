# Script to ping all IP addresses in a /24 subnet
import os

network = input("Enter first 3 numbers of IP network, e.g., 1.2.3: ")
print(network)
start_range = int(input("What is the start IP: "))
end_range = int(input("What is the end IP: "))
list_up_hosts = []

# Iterate over all usable IPs in this subnet
for host in range(start_range, end_range + 1):  # 254):
    # print("Pinging " + network + "." + str(host))
    res = os.system("ping -c 1 " + network + "." + str(host))
    if res == 0:
        print("\n" + network + "." + str(host) + " is up\n")
        list_up_hosts.append(network + "." + str(host))

# os.system(clear)
for each in list_up_hosts:
    print(each + " is up")
