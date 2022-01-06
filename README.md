# **Module 3 Practicum Report**

## Group 12 [IT02-01]

**Rifqi Naufal A 1202190012 || Andi Tadang P 1202190046**

<hr> 

make 2 copy of container php7.4

![image](https://user-images.githubusercontent.com/93064971/148401245-5b959f0a-483c-4d3e-99c3-c3028ed08a19.png)

go to php7.4_2 then Configurasi IP dan nginx ubuntu_landing_2

![image](https://user-images.githubusercontent.com/93064971/148399466-2cb7186e-c6e9-4b2a-93ce-4ae472af2fe5.png)

```
netplan apply
```

![image](https://user-images.githubusercontent.com/93064971/148399519-59cebbbe-b23e-4b1d-8d2d-e7a5db3e2450.png)

![image](https://user-images.githubusercontent.com/93064971/148399538-e8f4c565-ee93-41a6-9328-13b9eaa9db21.png)

in  nano /etc/nginx/sites-available/lxc_php7.dev

![image](https://user-images.githubusercontent.com/93064971/148399748-dff394db-a9ce-4441-b3af-b03fbfa3b398.png)

```
nginx -t
service nginx restart
```

![image](https://user-images.githubusercontent.com/93064971/148399797-b0ef155b-0497-4a08-9f49-7571c5223c10.png)

```
exit
```

now do the same for php7.4_3 clone

![image](https://user-images.githubusercontent.com/93064971/148399895-fed6acc4-101a-44fa-8f96-599f8190e2f4.png)

![image](https://user-images.githubusercontent.com/93064971/148399905-cca36b76-fc14-40e7-a226-8d10681fa021.png)

![image](https://user-images.githubusercontent.com/93064971/148399918-3e83d467-537b-425a-ad8d-d4de8595845e.png)

![image](https://user-images.githubusercontent.com/93064971/148399928-eb6faa2e-6873-485c-99af-59a8910bd639.png)

![image](https://user-images.githubusercontent.com/93064971/148399944-85e76153-fabc-4197-8bd4-af8c3d49b2a6.png)

now we make clone debian

```
sudo lxc-stop -n debian_php5.6
sudo lxc-copy -n debian_php5.6 -N debian_php5.6_2 -sKD
sudo lxc-copy -n debian_php5.6 -N debian_php5.6_3 -sKD
```

![image](https://user-images.githubusercontent.com/93064971/148400020-33dce8d6-814a-4ca7-ae14-9f1cceb8220f.png)

go to  sudo lxc-attach -n debian_php5.6_2 and change the IP address to '10.0.3.112'. The same for 'debian_php5.6_3' and change the IP address to '10.0.3.122'

![image](https://user-images.githubusercontent.com/93064971/148400052-350dcee1-adf7-48b6-90a9-1a69a979fe03.png)

add  'lxc_php5_2.dev' at /etc/hosts

![image](https://user-images.githubusercontent.com/93064971/148400073-9c2c7a9f-0258-4fb8-9ed4-3af4e958a75f.png)

![image](https://user-images.githubusercontent.com/93064971/148400110-7d57ebf4-9689-4cf9-939c-e13f52cd2120.png)

![image](https://user-images.githubusercontent.com/93064971/148400182-7ba194c6-c0a6-4384-b299-72aec3c5dc2f.png)

![image](https://user-images.githubusercontent.com/93064971/148400216-4fddf542-48bf-45c3-9622-28c8580b79c9.png)

```
exit
```

now do the same for debian_php5.6_3 clone

![image](https://user-images.githubusercontent.com/93064971/148400316-832d8f9d-0142-4fa5-bf21-d3b905f5f30c.png)

![image](https://user-images.githubusercontent.com/93064971/148400325-d928e47c-5105-416c-8616-d1214a03e65b.png)

![image](https://user-images.githubusercontent.com/93064971/148400338-79988046-39f7-483d-ac49-ffcacb027b8e.png)

![image](https://user-images.githubusercontent.com/93064971/148400346-2edaaa38-62c7-4fb8-bd95-4925273f49ac.png)

![image](https://user-images.githubusercontent.com/93064971/148400362-394673e9-d86d-4381-9232-b8c4ce6be541.png)

```
exit
```

Add all the containers in /etc/hosts (on vm)

![image](https://user-images.githubusercontent.com/93064971/148400398-593adf0e-f445-41ae-876e-2c37ee2550a3.png)

now Run the jmeter, and change the number of threads first 50 then 100 and 150

![image](https://user-images.githubusercontent.com/93064971/148400474-0b213849-44f6-486b-b29a-619104090066.png)

![image](https://user-images.githubusercontent.com/93064971/148400486-88134485-c2f6-4d42-9bd3-72a3b00d4d51.png)

![image](https://user-images.githubusercontent.com/93064971/148400497-5dc85675-d017-42fe-a6c7-31b37d6a53c4.png)

- 100

![image](https://user-images.githubusercontent.com/93064971/148400526-06f21ea4-4600-4ff2-9927-aff20fa4594c.png)

![image](https://user-images.githubusercontent.com/93064971/148400582-59a7b0a4-4b68-40bc-82f0-9e7aba6f6650.png)

![image](https://user-images.githubusercontent.com/93064971/148400613-9bf8aadf-d6aa-438f-a532-9041b080aff4.png)

- 150

![image](https://user-images.githubusercontent.com/93064971/148400640-6988d176-6cc4-4c3c-b122-511ea34a7895.png)

![image](https://user-images.githubusercontent.com/93064971/148400650-a756d782-2998-4a35-a953-dd6cfd1cf3b8.png)

![image](https://user-images.githubusercontent.com/93064971/148400659-6e7df024-7b0d-47c2-a7d4-e836b47524d0.png)

now we add the loader and change proxy_pass for php5 and php7 go to

```
nano /etc/nginx/sites-available/vm.local
```

![image](https://user-images.githubusercontent.com/93064971/148400797-e6f424ba-51e4-49aa-b6ee-e1a2b1382c03.png)

![image](https://user-images.githubusercontent.com/93064971/148400861-aead499c-c907-4b80-9a74-371b0b8041d6.png)

then we go back to jmeter and do the same thing, first do the 50 then 100 and 150

![image](https://user-images.githubusercontent.com/93064971/148400886-89f9f561-7dd9-432a-a6df-0e0cf54d9bee.png)

![image](https://user-images.githubusercontent.com/93064971/148400901-0217cc5f-a3f8-449a-9a38-0635fd0d6a77.png)

![image](https://user-images.githubusercontent.com/93064971/148400917-3d39bda7-4c84-452d-99b4-81a8cd894f30.png)

- 100

![image](https://user-images.githubusercontent.com/93064971/148400939-2eccc2c2-6970-45d6-8bd1-570b542391e8.png)

![image](https://user-images.githubusercontent.com/93064971/148400949-58239dd7-4135-48ea-9be1-1620273ac4a1.png)

![image](https://user-images.githubusercontent.com/93064971/148400961-2ff748d1-fb74-4dd9-b672-0daf0692d518.png)

-150

![image](https://user-images.githubusercontent.com/93064971/148400975-05d7a2e0-b2af-4767-8d8b-c94aefebf4c6.png)

![image](https://user-images.githubusercontent.com/93064971/148400990-2ad9adac-4d91-4bb8-a019-2832f47ed223.png)

![image](https://user-images.githubusercontent.com/93064971/148401000-dc9284b9-4bba-449b-9aae-4ec54cb5bd78.png)

### Analysis

Below is the results from when we use load balancer and not using the load balancer

 - When there is 50 users that access our web, if we don't use load balancer the average time of user accessing our web is
   - landing : 1115 ms / 1.1 s
   - blog : 1555 ms / 1.5 s
   - app : 4 ms / 0.004 s
- When we use load balancer, then
   - landing : 37 ms / 0.037 s
   - blog : 27 ms / 0.027 s
   - app : 21 ms / 0.021 s

Here we can know that the average time of user accessing our web is faster then if we don't use load balancer. For the throughput or the amount of user accessing our web is
- When there is 50 users that access our web, if we don't use load balancer the amount of user accessing our web is

  - landing : 36 user / second
  - blog :  20 user / second
  - app : 41 user / second

- When we use load balancer, then

  - landing : 427 user / second
  - blog :  439 user / second
  - app : 446 user / second

The conclusion is, if we use load balancer, then the time is faster and the amount of users that accessing our web is much more then when we don't use load balancer.

*Thank you* :)
