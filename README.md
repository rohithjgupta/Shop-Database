# Shop-Database



create table tbl_customer(

  custid number,

  custname varchar2(50),

  contactno number,

  email varchar2(50),

 constraint cust_id_pk1 PRIMARY KEY(custid)

 );

insert into tbl_customer values( 01,'Sarbani', 1111111111, 'sar@gmail.com');

insert into tbl_customer values( 02,'George', 2222222222, 'geo@gmail.com');

insert into tbl_customer values( 03,'Jacob', 3333333333, 'jac@mail.com');

insert into tbl_customer values( 04,'Marry', 4444444444, 'marry@gmail.com');

insert into tbl_customer values(05, 'Steve', 5555555555, 'ste@gmail.com');

insert into tbl_customer values( 06,'jois', 111111111, 'jois@gmail.com');

insert into tbl_customer values(07, 'Nancy', 7777777777, 'nan@gmail.com');

insert into tbl_customer values( 08,'Owais', 8888888888, 'owis@gmail.com');

insert into tbl_customer values(09, 'Bob', 9999999999, 'bob@gmail.com');

insert into tbl_customer values( 10,'Christina', 0000000000, 'Chris@gmail.com');

insert into tbl_customer values( 11,'Jack', 1212121212, 'jack@gmail.com');

insert into tbl_customer values( 12,'Olive', 3434343434, 'olive@gmail.com');

insert into tbl_customer values( 13,'Harry', 0101010101, 'harry@gmail.com');

create table tbl_location(

custid number,

city varchar2(50),

state varchar2(50),

pincode number,

CONSTRAINT cust_id_fk1

 FOREIGN KEY (custid) 

 REFERENCES tbl_customer(custid)

);

 

insert into tbl_location values( 01,'chicago','illinois',60616);

insert into tbl_location values( 02,'chicago','illinois',60616);

insert into tbl_location values( 03,'austin','texas',65242);

insert into tbl_location values( 04,'dallas','texas',23423);

insert into tbl_location values( 05,'rochester','new york',35623);

insert into tbl_location values( 06,'houston','texas',42536);

insert into tbl_location values( 07,'null','california',63476);

insert into tbl_location values( 08,'raleigh','north carolina',73643);

insert into tbl_location values( 09,'null','new jersey',63647);

insert into tbl_location values( 10,'albany','new york',17628);

insert into tbl_location values( 11,'virginia','richmond', 23456);

insert into tbl_location values( 12,'Vermont','Montpelier',345785);

insert into tbl_location values( 13,'Wisconsin', 'Madison', 235689);

create table tbl_order(

custid number,

orderid number,

order_ref varchar2(50),

orderhistory varchar2(50),

orderdate Date,

constraint order_id_pk3 PRIMARY KEY(orderid),

CONSTRAINT cust_id_fk2

 FOREIGN KEY (custid) 

 REFERENCES tbl_customer(custid)

 );

insert into tbl_order values( 01,101,'ordered','delivered','13-Jan-2014');

insert into tbl_order values( 02,102,'ordered','notdelivered','12-Jan-2013');

insert into tbl_order values( 02,122,'ordered','delivered','17-Jan-2014');

insert into tbl_order values( 03,103,'cancelled','null','15-Oct-2007');

insert into tbl_order values( 04,104,'ordered','delivered','21-Jan-2014');

insert into tbl_order values( 05,105,'cancelled','null','29-Jun-2004');

insert into tbl_order values( 06,106,'ordered','delivered','10-Jan-2013');

insert into tbl_order values( 07,107,'cancelled','null','22-Nov-2011');

insert into tbl_order values( 08,108,'ordered','notdelivered','30-Mar-2013');

insert into tbl_order values( 08,188,'ordered','delivered','12-jun-2013');

insert into tbl_order values( 09,109,'cancelled','null','12-Feb-2012');

insert into tbl_order values( 10,110,'ordered','delivered','23-Apr-2014');

insert into tbl_order values( 11,111,'ordered','notdelivered','12-mar-2014');

insert into tbl_order values( 12,112,'cancelled','null','10-Jan-2014');

insert into tbl_order values( 13,113,'ordered','cancelled', '22-feb-2014');

create table tbl_storeitems(

itemname varchar2(50),

itemid number,

quantity number,

orderstatus varchar2(30),

constraint item_id_pk4 PRIMARY KEY(itemid)

);

insert into tbl_storeitems values('laptop',4446,8,'yes');

insert into tbl_storeitems values('washingmachine',7888,9,'no');

insert into tbl_storeitems values('xbox',2226,11,'yes');

insert into tbl_storeitems values('web designing and internet',8854,17,'no');

insert into tbl_storeitems values('playstation',1622,15,'yes');

insert into tbl_storeitems values('cellphone',8587,12,'no');

insert into tbl_storeitems values('chair',6594,9,'no');

insert into tbl_storeitems values('refrigerator',7345,17,'yes');

insert into tbl_storeitems values('database designing book',2673,6,'yes');

insert into tbl_storeitems values('desktop_pc',1376,19,'no');

insert into tbl_storeitems values('software programming book',1642,17,'yes');

insert into tbl_storeitems values('table_fan',3302,15,'no');

insert into tbl_storeitems values('hairdryer',1127,12,'yes');

insert into tbl_storeitems values('music_system',6043,6,'no');

insert into tbl_storeitems values('heater',4452,11,'yes');

create table tbl_vendors(

vendorid number,

vendorname varchar2(50),

commodity_name varchar2(50),

itemid number,

CONSTRAINT item_id_fk8

 FOREIGN KEY (itemid) 

 REFERENCES tbl_storeitems(itemid)

 );

insert into tbl_vendors values(201,'ebay','laptop',4446);

insert into tbl_vendors values(null,null,'washingmachine',7888);

insert into tbl_vendors values(202,'amazon','xbox',2226);

insert into tbl_vendors values(null,null,'web designing and internet',8854);

insert into tbl_vendors values(203,'googleplay','playstation',1622);

insert into tbl_vendors values(null,null,'cellphone',8587);

insert into tbl_vendors values(null,null,'washingmachine',6594);

insert into tbl_vendors values(204,'flipkart','refrigerator',7345);

insert into tbl_vendors values(205,'shopclues','database designing book',2673);

insert into tbl_vendors values(null,null,'desktop_pc',1376);

insert into tbl_vendors values(206,'snapdeal','software programming book',1642);

insert into tbl_vendors values(null,null,'table_fan',3302);

insert into tbl_vendors values(207,'besybuy','hairdryer',1127);

insert into tbl_vendors values(null,null,'music_system',6043);

insert into tbl_vendors values(208,'walmart','heater',4452);

create table tbl_billing(

custid number,

itemid number,

orderid number,

productname varchar2(50),

paid varchar2(50),

purchase_quan number,

total_amt number,

CONSTRAINT item_id_fk3

 FOREIGN KEY (itemid) 

 REFERENCES tbl_storeitems(itemid),

 CONSTRAINT cust_id_fk4

 FOREIGN KEY (custid) 

 REFERENCES tbl_customer(custid),

 CONSTRAINT order_id_fk7

 FOREIGN KEY (orderid) 

 REFERENCES tbl_order(orderid)

 );

 insert into tbl_billing values(01,4446,101,'laptop','yes',2,1050);

 insert into tbl_billing values(02,4446,102,'laptop','yes',1,550);

 insert into tbl_billing values(04,2226,104,'xbox','yes',1,500);

 insert into tbl_billing values(06,1622,106,'playstation','yes',3,3000);

 insert into tbl_billing values(08,7345,108,'refrigerator','yes',1,700);

 insert into tbl_billing values(02,2673,122,'database designing book','no',1,500);

 insert into tbl_billing values(10,1642,110,'software programming book','yes',5,5000);

 insert into tbl_billing values(11,1127,111,'hairdryer','no',2,1500);

 insert into tbl_billing values(13,4452,113,'heater','no',3,3500);

 insert into tbl_billing values(08,1622,188,'playstation','yes',2,2000);

 

 

 

 create table tbl_paymentmode(

 custid number,

 paymode varchar2(50),

 CONSTRAINT cust_id_fk5

 FOREIGN KEY (custid) 

 REFERENCES tbl_customer(custid)

 );

 insert into tbl_paymentmode values(01,'cheque');

 insert into tbl_paymentmode values(02,'debit');

 insert into tbl_paymentmode values(04,'credit');

 insert into tbl_paymentmode values(06,'cash');

 insert into tbl_paymentmode values(08,'debit');

 insert into tbl_paymentmode values(10,'cheque');

 insert into tbl_paymentmode values(08,'cash');
