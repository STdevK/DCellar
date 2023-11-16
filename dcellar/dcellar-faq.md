---
title: "FAQ"
slug: "dcellar-faq"
hidden: false
createdAt: "2023-04-11T15:50:40.900Z"
updatedAt: "2023-10-27T02:55:30.257Z"
---
## Wallet Related

***

#### Question: Where can I get my test token?

**Answer**: To claim test BNB tokens on the Greenfield BSC Testnet, you can use our \[[Faucet](https://gnfd-bsc-faucet.bnbchain.org/)]

***

#### Question: Why can't I connect wallet?

**Answer**: Due to testnet network upgrade, your wallet may not be able to connect. Please follow the instructions below:

1. Open your wallet extension, click the network panel;
2. Delete the network (Including the **greenfield testnet** and **greenfield bsc testnet**) 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/e8d7ab5-Networks.png",
        null,
        "delete the network"
      ],
      "align": "center",
      "sizing": "200px",
      "caption": "delete the network"
    }
  ]
}
[/block]


3. Now you can click the connect wallet button in DCellar again to add the new network.

#### Question: Why can't I withdraw over 100 BNB?

**Answer**:Due to safety concern, user cannot withdraw over 100 BNB at a time. You can try seperate your operation to multiple operations to continue your withdrawal.

***

## Account Related

***

#### Question: What does Owner Account  and Payment Account mean?

**Answer:**When you connect wallet to login, the account you are using is Owner Account. By default, owner address will be used to pay for the objects it owns. But you can also create multiple "payment accounts" and associate objects to different payment accounts to pay for storage and bandwidth.

You can select different payment account when you create bucket. After setting, all storage fee within this bucket will be paid from this payment account. 

Please Notice that gas fees are always paid by owner account.

The address format of the payment account is the same as normal accounts. It's derived by the hash of the user address and payment account index. However, the payment accounts are actually only logical ones and only exist in the storage payment module. Users can deposit into, withdraw from and query the balance of payment accounts on the Greenfield blockchain, but users cannot use payment accounts to perform staking or other on-chain transactions. Payment accounts can be set as "non-refundable". Users cannot withdraw funds from such payment accounts.

#### Question: What is Greenfield available balance?

**Answer:**When you store a data object on Greenfield, part of your balance will be "locked". Which means, your account balance will keep the same, but you can only spend the "unlocked" part. Greenfield available balance means  balance you can use to pay for gas fees and other operations. 

#### Question: What is Non Refundable Payment Account?

**Answer:**When a payment account is set as non-refundable, you can only transfer token into the account, but you  can not transfer token out from the account. This setting is unrecoverable.

#### Question: What is Temporal account?

**Answer:**Create a temporary account at runtime and grant it full permissions to create objects on behalf of your primary account. In this approach, your primary account only needs to send a transaction to Greenfield to grant permissions to the temporary account. For each object to be uploaded, the temporary account will be used to broadcast the transaction to the Greenfield Chain. There is no further interaction required from the primary account. Please note, the temporary account does not need to be deposited. To Learn more please goto -> [Greenfield Doc](https://docs.bnbchain.org/greenfield-docs/docs/tutorials/native-dapp/sdk/batch-upload#temporary-account-showcase)

## Bucket Related

***

#### Question: What is the naming rules for bucket?

**Answer:**Bucket's naming rule is as below:

Bucket names must be between 3 (min) and 63 (max) characters long.  
Bucket names can consist only of lowercase letters, numbers,  and hyphens (-).  
Bucket names must begin and end with a letter or number.  
Bucket names must be global unique in Greenfield  
A bucket name cannot be used by another Greenfield account until the bucket is deleted.

***

#### Question: What is the naming rules for files?

**Answer:**File's naming rule is as below:

File name must be between 1 (min) and 1024 (max) characters long.  
UTF-8 characters are supported, except "/"

***

#### Question: What is discontinue?

**Answer:** Storage providers can actively discontinue buckets/files in testnet environment for remove historical data. Once your file is marked as discontinue, it will be deleted soon, so be sure to back it up in advance. 

> 📘 **_Please be assured that this will only happen on testnet and NOT on mainnet._**

***

## File Related

***

#### Question: Why my upload request failed?

**Answer:**upload request might fail for multiple reasons, if the upload task is failed, it cannot be resumed, you can only create a new upload task.  Before retry, you can log out and login again, this action will re-active your off chain auth status,  reduce the probability of errors reoccurring.

## Fee Related

***

#### Question: How many types of fees will I be charged?

**Answer:** In Greenfield, users are required to pay three different types of fees:

- Firstly, every transaction will require gas fees to pay the Greenfield validator to write the metadata on-chain, and for cross chain operations, gas will include gas fee on Greenfield and Relayer Fee which is paid to cross chain repalyers.  
  **Please Notice that gas fees are always paid by owner account.**
- Secondly, when you upload files, the Storage Providers (SPs) charge the users for their storage service, usually it will prelock 6 months' storage fee for each file, and the prelocked storage fee will be paid under a certain flow rate. Storage fee will be paid by the payment account associated with the bucket.
- Thirdly, when you download/preview files, or when others download/preview your files ( if your files are public or you have granted access to them), Storage Providers will charge the file owner which is you download bandwidth fee( Quota). Usually, when you create bucket, system will give you some Free Quota, and you can also buy some extra monthly quota which will expire each month. Quota fee will be paid by the payment account associated with the bucket.

Please Notice that those fees are all charged by Greenfield. Currently DCellar do not charge user for any service fees.  

#### Question: How is Greenfield storage fee been charged?

**Answer:**For storage, every object stored on Greenfield is charged at the price calculated by size, replica numbers, a base price ratio, and other parameters. Once the object is stored, the total charge of storage will be mainly only related to time and the base price.

Storage fee will be send to Storage providers as their income. Besides storage fee, users will be charged with validator tax fee, which is about 1% of storage fee, validator tax fee will be send to validators. 

#### Question: What is flow rate?

**Answer:**The per-second rate at which a sender decreases its net outflow stream and increases a receiver's net inflow stream when creating or updating a payment stream.

#### Question: How is Greenfield Quota been charged?

**Answer:**Users are granted a free, time-based quota for downloading data, with each bucket corresponding to a set of their objects. If the quota is exceeded, users can upgrade their data package to obtain additional quota. The price for each data package is fixed for a certain period (unless the primary storage provider updates the read price and the user takes some actions to reflect the price change), during which users will only be charged based on the amount of time they spend downloading and the package price. This charging scheme remains in effect until the user modifies their data package settings.

If you want to down-grade your monthly quota, you need to wait until 30 days after your last quota management operation.

## Storage Provider Related

***

#### Question: As a Storage Provider, how to provide storage service in DCellar?

Firstly, please follow [BNB Greenfield Documentation](https://docs.bnbchain.org/greenfield-docs/docs/guide/storage-provider/run-book/run-testnet-SP-node) to Join Greenfield as a Storage Provider.

Secondly, please  run a [standard test](https://github.com/bnb-chain/greenfield-sp-standard-test) to make sure your SP is running as expected.

Thirdly, you should make sure your service **nginx** have configured your http response header. It's also included in the standard test, [check it out ->](https://github.com/bnb-chain/greenfield-sp-standard-test/blob/main/config/config.yml)

```
nginx.ingress.kubernetes.io/cors-allow-headers: "DNT,Keep-Alive,User-Agent,X-Requested-With,If-Modified-Since,Cache-Control,Content-Type,Range,Authorization,X-Gnfd-Unsigned-Msg,X-Gnfd-Txn-Hash,Date,X-Gnfd-Object-ID,X-Gnfd-Piece-Index,X-Gnfd-Redundancy-Index,Address,X-Gnfd-User-Address,X-Gnfd-App-Domain,X-Gnfd-App-Reg-Nonce,X-Gnfd-App-Reg-Public-Key,X-Gnfd-App-Reg-Expiry-Date"
nginx.ingress.kubernetes.io/cors-expose-headers: "*, X-Gnfd-Request-ID,X-Gnfd-Signed-Msg,X-Gnfd-Object-ID,X-Gnfd-Integrity-Hash,X-Gnfd-Piece-Hash"
nginx.ingress.kubernetes.io/enable-cors: "true"
```

Here is an example of response header config, you should make sure all these methods are accessible:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b378196-2023-07-18_10.06.28.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


Then, you can double check if your storage provider is listed in [GreenfieldScan Storage Provider List Page](https://greenfieldscan.com/storage-providers). 

 If all goes well, you should be able to find your storage provider listed in DCellar. You can check if it shows in the SP list when you **Create Bucket**:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8bc2a5d-2023-08-09_10.41.45.png",
        "",
        ""
      ],
      "align": "center",
      "sizing": "500px"
    }
  ]
}
[/block]


#### Question: Why the service display status is abnormal in DCellar?

Firstly, please make sure your endpoint can visit properly, DCellar will send a request  as follow to check if your storage provider service status is active 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/a696f79-2023-08-09_11.01.58.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


If you cannot find your SP in SP list, or you find your SP service status shows abnormal, it's possible that you did not config your http response header properly.

To Debug, you can log out, go back to Dcellar welcome page, open your brower inspect function, retry login , and see what error message is displayed. 

If it shows as follow: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2dbb286-2023-08-09_10.25.59.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


Then you can find out it's a response header config error.  please config your nginx as above.