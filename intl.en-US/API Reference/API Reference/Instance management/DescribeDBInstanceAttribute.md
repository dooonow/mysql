# DescribeDBInstanceAttribute {#reference_ul2_zj2_12b .reference}

## Description {#section_l21_v32_12b .section}

Show the detailed attributes of a specified instance.

## Request parameters {#section_qzx_w32_12b .section}

|Name|Type|Required?|Description|
|----|----|---------|-----------|
|Action|String|Yes|Required parameter. Value: DescribeDBInstanceAttribute.|
|DBInstanceId|String|Yes|Instance ID. Up to 30 IDs can be entered at a time, which are separated by commas \(,\).|

**Parameter of DBInstanceAttribute**

|Name|Type|Description|
|----|----|-----------|
|DBInstanceId|String|Instance ID.|
|PayType|String| -   Postpaid: Pay-As-You-Go; 
-   Prepaid: Subscription.

 |
|Dbinstancetype|String| -   Primary: primary instance; 
-   Readonly: read-only instance; 
-   Guard: disaster recovery instance;
-   Temp: temporary instance.

 |
|Category|String| -   Basic: basic edition\(single-node\);
-   Standard: standard edition \(high-available\);
-   Enterprise: enterprise edition.

 |
|InstanceNetworkType|String| -   Classic: classic network;
-   VPC: VPC network.

 |
|ConnectionMode|String| -   Performance: standard access mode;
-   Safty: high security access mode.

 |
|RegionId|String|Region.|
|ZoneId|String|Zone.|
|ConnectionString|String|Connection address.|
|Port|String|Application access port.|
|Engine|String|Database type.|
|Engineversion|String|Database version.|
|DBInstanceClassType|String|Class Family.-   s: Shared DB;
-   x: General Instance;
-   d: Dedicated Instance;
-   h: Dedicated Host..

|
|DBInstanceClass|String|Instance type.|
|DBInstanceMemory|Long|Instance memory, in the unit of MB.|
|DBInstanceStorage|Integer|Instance storage space, in the unit of GB.|
|DBInstanceNetType|String| -   Internet: public network;
-   Intranet: private network.

 |
|DBInstanceStatus|String|For instance status, see [Instance status table](intl.en-US/API Reference/API Reference/Schedules/Instance status table.md#).|
|DBInstanceDescription|String|Instance remarks.|
|LockMode|String| -   Unlock: normal;
-   ManualLock: locked when manually triggered;
-   LockByExpiration: automatically locked upon expiration;
-   LockByRestoration: automatically locked before instance rollback;
-   LockByDiskQuota: automatically locked when the instance space is full.

 |
|LockReason|String|Reason why an instance is locked.|
|DBMaxQuantity|Integer|The maximum number of databases that can be created for an instance.|
|AccountMaxQuantity|Integer|Max number of accounts that can be created.|
|CreationTime|String|Creation time, in the format of YYYY-MM-DDThh:mm:ssZ, for example, 2011-05-30T12:11:4Z.|
|ExpireTime|String|Expiration time. Pay-As-You-Go instances never expire.|
|MaintainTime|String|Instance maintenance time. For example, 00:00Z-02:00Z indicates that routine maintenance can be performed from 0:00 to 2:00.|
|AvailabilityValue|String|Instance availability status of the current year. Unit: percentage.|
|MaxIOPS|Integer|The maximum number of I/O requests, that is, IOPS.|
|MaxConnections|Integer|The maximum number of concurrent connections to an instance.|
|MasterInstanceId|String|ID of the primary instance. If this parameter is not returned \(that is, if it is null\), the current instance is a primary instance.|
|IncrementSourceDBInstanceId|String|Instance ID of the incremental data source. For example, a disaster recovery instance’s incremental data source is a primary instance. A read-only instance’s incremental data source is a primary instance, and a primary instance’s incremental data source is NULL.|
|GuardDBInstanceId|String|If a disaster recovery instance is attached to the current instance, the ID of the disaster recovery instance applies.|
|TempDBInstanceId|String|If a temporary instance is attached to the current instance, the ID of the temporary instance applies.|
|ReadOnlyDBInstanceIds|List<OnlyDBInstanceId\>|ID list of read-only instances attached to the primary instance.|
|SecurityIPList|String|Deprecated. For more information, see DescribeDBInstanceIPArrayList interface.|
|AdvancedFeatures|String|This parameter is currently only valid for SQL Server instances. Obtain advanced properties values, and multiple values are separated by English comma \(,\). The return value is - LinkedServer -. DistributeTransaction|

**ReadOnlyDBInstanceId**

|Name|Type|Description|
|----|----|-----------|
|<Public Return Parameters\> | |For more information, see [Public parameters](intl.en-US/API Reference/Use APIs/Public parameters.md#).|
|DBInstanceId|String|ID of a read-only instance.|

## Return parameters {#section_rpk_z32_12b .section}

|Name|Type|Description|
|----|----|-----------|
|<Public Return Parameters\>|-|For more information, see [Public parameters](intl.en-US/API Reference/Use APIs/Public parameters.md#).|
|Items|List<DBInstanceAttribute\>|-|

## Request example {#section_l4g_pj2_12b .section}

```
https://rds.aliyuncs.com/?Action=DescribeDBInstanceAttribute
&DBInstanceId=rdsaiiabnaiiabn
&<Public Request Parameters>
```

## Return example {#section_xtg_rj2_12b .section}

**XML format**

```
<CreateDBInstanceResponse>
  <RequestId>3C5CFDEE-F774-4DED-89A2-1D76EC63C575</RequestId>
  <Items>
    <DBInstanceAttribute>
    <LockMode>Unlock</LockMode>
    <ConnectionString>rdsfnjfqu7vjnuj.mysql.rds.aliyuncs.com </ConnectionString>
    <CreationTime>2014-10-10T10:28:48Z</CreationTime>
    <DBInstanceNetType>Internet</DBInstanceNetType>
    <MaxConnections>60</MaxConnections>
    <LockReason></LockReason>
    <Engine>MySQL</Engine>
    <Value> 100.0% </value>
    <AccountMaxQuantity>50</AccountMaxQuantity>
    <DBMaxQuantity>200</DBMaxQuantity>
    <RegionId>cn-hangzhou </RegionId>
    <ZoneId>cn-hangzhou-a</ZoneId>
    <ReadOnlyDBInstanceIds>
    <ReadOnlyDBInstanceId></ReadOnlyDBInstanceId>
    </ReadOnlyDBInstanceIds> 
    <TempDBInstanceId></TempDBInstanceId>
    <DBInstanceMemory>240</DBInstanceMemory>
    <MaxIOPS>150</MaxIOPS>
    <DBInstanceType>Primary</DBInstanceType>
    <DBInstanceStatus>Running</DBInstanceStatus>
    <MasterInstanceId></MasterInstanceId>
    <EngineVersion>5.5</EngineVersion>
    <IncrementSourceDBInstanceId></IncrementSourceDBInstanceId>
    <GuardDBInstanceId></GuardDBInstanceId>
    <DBInstanceStorage>10</DBInstanceStorage>
    <DBInstanceDescription></DBInstanceDescription>
    <DBInstanceId>rdsfnjfqu7vjnuj</DBInstanceId>
    <Paytype> postpaid </paytype>
    <ExpireTime></ExpireTime>
    <MaintainTime></MaintainTime>
    <DBInstanceClass>rds.mys2.small</DBInstanceClass>
    <SecurityIPList>11.11.11.11</SecurityIPList>
    <Port>3306</Port>
    <AdvancedFeatures>LinkedServer,DistributeTransaction</AdvancedFeatures>
    </DBInstanceAttribute>
</CreateDBInstanceResponse>
```

**JSON format**

```

  "Items": {
    "DBInstanceAttribute": [
      
        "LockMode": "Unlock", 
        "ConnectionString": "rdsfnjfqu7vjnuj.mysql.rds.aliyuncs.com", 
        "CreationTime": "2014-10-10T10:28:48Z", 
        "DBInstanceNetType": "Internet", 
        "ReadOnlyDBInstanceIds": {
          "ReadOnlyDBInstanceId": []
         
        "MaxConnections": 60, 
        "LockReason": "", 
        "Engine": "MySQL", 
        "AvailabilityValue": "100.0%", 
        "AccountMaxQuantity": 50, 
        "DBMaxQuantity": 200, 
        "RegionId": "cn-hangzhou", 
        "TempDBInstanceId": "", 
        "DBInstanceMemory": 240, 
        "MaxIOPS": 150, 
        "DBInstanceType": "Primary", 
        "DBInstanceStatus": "Running", 
        "MasterInstanceId": "", 
        "EngineVersion": "5.5", 
        "IncrementSourceDBInstanceId": "", 
        "GuardDBInstanceId": "", 
        "DBInstanceStorage": 10, 
        "DBInstanceDescription": "", 
        "DBInstanceId": "rdsfnjfqu7vjnuj", 
        "PayType": "Postpaid", 
        "ExpireTime": "", 
        "MaintainTime": "", 
        "Maid": "RDS. mys2.small ", 
        "SecurityIPList": "11.11.11.11", 
        "Port": "3306"
        "AdvancedFeatures": "LinkedServer,DistributeTransaction"
      
    
   
  "RequestId": "27BB49FA-DA47-4162-B39D-FC001E35C1C1"

```

