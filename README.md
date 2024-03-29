<img
align="right"
style="pointer-events:none;"
src="./images/logo/logo.jpg" width=40%
/>

# SUI Unity SDK 2023

[![License](https://img.shields.io/github/v/release/CSzlong/sui-unity_sdk?display_name=tag&style=for-the-badge)](https://github.com/CSzLong/sui-unity_sdk/releases/tag/v0.2.0)

## How to integrate Sui Unity SDK into Unity?

1. Download the latest version of the `Sui Unity SDK 2023` file `sui-unity-sdk.unitypackage` from releases of this repository:.

   https://github.com/CSzLong/sui-unity_sdk/releases

2. Import Sui Unity SDK into your Unity project:<br/>
   Navigation: **Assets -> Import Package -> Custom Package** <br/>
   ![import](images/ImportCustomPKG.png)
   select the downloaded `Sui Unity SDK 2023` package.

3. Set up the Unity scene to work with the Sui SDK.<br/>
   You can do this by adding the **`SuiCanvas`** prefab to your scene. 
   This prefab contains a canvas and a script that initializes the Sui SDK.

4. Involve class **`SuiManager`** from `Sui Unity SDK 2023` to initialize Sui SDK and set up any necessary configurations in your script.

For a more detailed explanation, including sample code, please refer to the documentation provided by Sui in the SDK package or on their website.


### Key Features

1. Backend and frontend separation functionality

2. Data upload functionality

3. Data retrieval functionality

4. Event reporting

5. Custom UI component library


## When using the Sui Unity SDK, please note the following:

1. Make sure you have imported the SDK correctly and follow the usage instructions provided in the Sui documentation.

2. Before using the SDK, please read the documentation to ensure that you are familiar with all the features and requirements of the SDK.

3. Be careful that do not to leak sensitive data and consider checking and deleting all code or information that may contain sensitive data before publishing.


## Examples

The code examples for using RPCs in Unity depend on which RPC library you choose to use. Here are two examples that may be helpful:

1. Photon Unity Networking（PUN）

```c#
using Photon.Pun;
using UnityEngine;

public class SomeScript : MonoBehaviourPun
{
[PunRPC]
void SomeRPCFunction(string someParameter)
{
Debug.Log("Received RPC with parameter: " + someParameter);
}

    void CallRPC()
    {
        photonView.RPC("SomeRPCFunction", RpcTarget.All, "someParameter");
    }
}
```

In this example, we define an RPC function called **`SomeRPCFunction`** and call it in the **`CallRPC`** function. The function has a string parameter that will be passed to other clients when the function is called. When calling the RPC, we use the **`photonView.RPC`** function and set the target to **`RpcTarget.All`** (send the RPC to all clients).


```c#
using Mirror;
using UnityEngine;

public class SomeScript : NetworkBehaviour
{
[TargetRpc]
void RpcSomeFunction(NetworkConnection target, string someParameter)
{
Debug.Log("Received RPC with parameter: " + someParameter);
}

    void CallRPC()
    {
        RpcSomeFunction(connectionToServer, "someParameter");
    }
}
```

In this example, we define an RPC function called **`RpcSomeFunction`** and call it in the **`CallRPC`** function. The function has a string parameter that will be passed to the server when the function is called, and will be sent to the target client via the **`target`** parameter. When calling the RPC, we use the **`RpcSomeFunction`** function and set the target to the connection of the client we want to send the RPC to.

Please note that these examples are conceptual proof-of-concepts and should not be copy-pasted directly into your code. You should modify these examples to suit your specific needs in order to use RPCs correctly in your project.

## Demo UI

![DemoUI](images/demoUI.png)

## sui-unity-sdk v0.3.0

![V0.3.0](images/wList.jpg)

### New Wallet connection

Plans to access Wallet list:
- Suiet
- Mofa
- Morphis
- FoxWallet
- MartianWallet
- Splash Wallet
- SensuiWallet
- ethos
- WELLDONE Wallet
- Keystone

Some more wallet in perfect, some only browser version, undeveloped app version, need research to try to access.

### Smart Contractor update

- NFT Kiosk
- NFT - Coin swap

## sui-unity_sdk v0.4.0

1. Support the unity version 2021.3.8f1c1
   
2. MicroMoveLab logo

   ![logo](./images/new01.jpg)

3. UI for NFT swap
   ![Create Pool](./images/new02.jpg)
   ![Step 1](./images/new03.jpg)
   ![Step 2](./images/new04.jpg)
   ![Step 3](./images/new05.jpg)

## Update on 10-Nov-2023

Update smart contract to match SUI v14.

Coming changes: Enhance the AMM Contract.