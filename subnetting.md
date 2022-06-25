# Subnet Mask

IP addresses are converted to Binary from Decimal/


 2^7	2^6	2^5	2^4	2^3	2^2	2^1    2^0

128	64		32		16		8		4		2         1

************/////********//////**********

Class A IP Range: 1st Network part of IP address starts with 127

Class B IP Range: 1st Network part of IP address starts with 190

Class C IP Range : 1st Network part of IP address starts with 222

Class D are reserved for Routers for Multitasking

Class E is reserved for future use and not used in any of the devices and hence considered as Wasted.

********/////*********/////***************

- To any device to communicate with other device, there IP addresses Network part and Subnet needs to match.

	If the 1st part of the IP address of its 4 part (*xxx*.xxx.xxx.xxx) is 	below 190 and only needs to match only the 1st part with the other device 	to communicate. then it's considered as assigned within Class A IP Range 	and 	it's *Subnet Mask* needs to occupy only 1st part of its octet (255.0.0.0).

	If the 1st part of the IP address of its 4 part (*xxx*.*xxx*.xxx.xxx) is 	below 127 and first 2 parts need to match with other device to communicate, then it's 	considered as assigned within Class B IP Range and 	it's *Subnet Mask* needs to occupy only 1st part of its octet (255.255.0.0).
	
	If the 1st part of the IP address of its 4 part (*xxx*.xxx.xxx.xxx) is 	below 222 and first 3 parts of its address needs to match with other 	device to communicate, then it's considered as assigned within Class C IP 	Range and 	it's *Subnet Mask* needs to occupy only 1st part of its octet (255.255.255.0).


By above we can say ### Subnet Mask represent Network bits.


********/////*******/////*****//********


## Slash values

Every octate in Subnet Mask is made of 8 bits, hence the value 255(2^8)

192.168.1 /8 	<-- is Slash Value, this determines the Subnet value, as this is 8 it represents 1st part of Subnet 255 as(2^8=255)
Similarly /9 represents (8+1) 255.128.0.0
/10 represents (8+2) 255.192.0.0


### For every 1 digit of Slash value after 8 and upto 16, we need to add each number from left of the 2^ verse:

For / 16 ( 8+8) we get 255.255.0.0

So, for Subnet Mask of 255.255.248.0 what should be the Slash value?
We have two octate full with 255, means we've already have 16 bits. We need to add the value of 248.

2^7	2^6	2^5	2^4	2^3	2^2	2^1    2^0

128	64		32		16		8		4		2         1

1		1		1		1		1		0	      0         0.    =  248

The above table shows the remaing bits to be added to 16, that is 5 bits which makes the answer (16+5)  21. The Slash value for IP address given would be /21.And subnet mask would be 255.255.248.0 .

## Always the first IP x.x.x.0 would be known as Subnet (NOT SUBNET MASK)/ Network ID and is Not assigned to hosts, similarly the last IP x.x.x.255 is known as Broadcast ID and is never assigned to Hosts.
### In accordance to above, the very next IP After Network ID is known as First Valid Host and the very next IP Before Broadcast IP is known as Last Valid IP. The IPs between First and Last valid IPs is known as Range.



