---
title: "DCellar For Developers"
slug: "dcellar-as-developer-tool"
hidden: false
createdAt: "2023-07-14T05:37:11.723Z"
updatedAt: "2023-07-17T04:34:43.898Z"
---
## DCellar : a powerful tool for developers on the BNB Greenfield

DCellar, as the inaugural application built on the BNB Greenfield, serves as an ultimate client of the BNB Greenfield network. This document aims to outline some of the key use cases of DCellar, which we believe will greatly assist developers in comprehending the functionalities of Greenfield:

- **NFT Storage and Minting**: With DCellar, developers and users can conveniently store their NFT resources and associated metadata, enabling them to easily mint their own NFTs. Compared to alternative solutions, DCellar provides a more intuitive interaction process, ensuring a seamless experience for users.
- **SP Connectivity Verification**: Greenfield network clients can leverage DCellar to upload and download files to their Service Provider (SP), thereby verifying the correct connection of the SP to the network. This feature enables users to ensure smooth and reliable communication with their chosen SP.
- **Web Server Functionality**: DCellar also functions as a web server, allowing users to effortlessly upload their frontend code to the platform. By setting the uploaded content to public access, anyone can access your web application simply by opening the universal link. This feature simplifies the process of hosting and sharing web applications.

### NFT Metadata and Medium Storage

This guide will provide a simple 2-step demonstration of how to create an NFT using DCellar, a user-friendly platform designed for uploading NFT resources and associated metadata. Compared to other platforms like IPFS, Filecoin, or Arweave, DCellar offers a more intuitive experience for NFT creation.

**Step 1**: Visit the DCellar website and create a bucket. A bucket serves as a container for your NFT files. Once created, proceed to create a folder within the bucket, such as "sunset," where you will store the NFT medium file (an image of a sunset). Upload the image file to the folder, ensuring that the file's access is set to "access by everyone" for public visibility.  
**Step 2**: Create the NFT metadata file, which is a JSON file containing descriptions of the NFT's properties, including its name, description, creator, and more. Create a JSON file and provide the relevant information within it. Upload this JSON file to the same folder as the image file and ensure that it is also set to public access.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/18c4dfb-image4.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]

```
{  
"name": "Sunset with Blue Mood",  
"description": "This is AI generated art to express the feeling when seeing the sunset",  
"image": "<https://gnfd-testnet-sp-6.bnbchain.org/view/artificial-aesthetics/sunset/sunset.jpeg>"  
}
```

The folder will be like this: 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1fdbf69-image5.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

This metadata follows the ERC-721 standard, which is a common format for NFTs on Ethereum and BSC. Then you can use the universal link of the json file as the token URI to mint your NFT. 

After you uploaded successfully, you can click view detail to get the universal endpoint of your data.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dcd18ac-image2.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]

### Verify Your storage provider (SP) with DCellar

The BNB Greenfield is an innovative platform that enables anyone to create their own decentralized storage service. All you need is some hardware and software to run a Storage Provider (SP). By joining the SP network, you can access the DCellar, a web interface that lets you manage your SP, create buckets and upload files. This is a great way to test your SP and make sure it is functioning properly.

To verify your SP configuration, you can follow these simple steps.

- First, you need to switch to the BNB Greenfield testnet in your wallet. This is a separate network from the mainnet, where you can experiment without risking real funds. 
- Then, go to the DCellar page and connect it with your wallet. This will allow you to interact with the SP network and see your SP details. You can also see all the SPs in the network by looking at the signing message that appears when you connect your wallet. 
- However, this message is not user-friendly. And DCellar can improve this:
  - After signing the message and connecting the wallet, head to the bucket page for bucket creation. Once done, start to pick the SP to store your files.
  - All the active SPs will show up here with your SP in this list.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/dcfa679-image1.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]

Finally, you can test the functions of uploading and downloading of files on your own SP.

### Web Hosting

You can use the BNB Greenfield to host your applications on the web. There are some good reasons to use the BNB Greenfield as your web server.

- **Censorship resistance**:  It is decentralized, so no one can censor or shut down your web application. It is always online and available.
- **Reliability**: Being decentralized means that it can handle any network failures. Even if some SPs go offline, your application is still reachable. 

With that, DCellar and BNB Greenfield are the perfect tools for building decentralized web applications. You can check out a sample architecture below.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/4ab7be9-image3.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

Let's start by hosting an HTML file. 

- First, you can create a bucket to store your web application frontend files. And upload the file through DCellar. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f1fa545-image6.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]

- When uploading, make sure to choose the permission of this file. It needs to be set as **everyone** can access it.
- After successfully uploading, you can get the universal URL of this file through the detail page. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/b36bcb5-image10.png",
        null,
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]

Click the view details button, and copy the universal link. 

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6702694-image7.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]

This link will be used as an access URL to your application.

## Summary

The article outlined some use cases of DCellar. As the first application of the Greenfield network, DCellar can be used as a powerful developer tool that can make developer life much easier. It allows developers and users to store NFT resources and metadata to mint NFTs, and host web applications with ease and security. DCellar is also a client of the Greenfield network, which can also help SP hosting service providers verify their SP\`s configuration and connectivity by uploading and downloading files to their storage providers (SPs). 

Let's keep exploring different possibilities of DCellar and we will keep sharing more guidance in the upcoming articles.