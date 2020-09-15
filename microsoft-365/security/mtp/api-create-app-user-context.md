---
title: ユーザーの代理として Microsoft の脅威保護 Api にアクセスする
description: ユーザーの代理として Microsoft の脅威保護 Api にアクセスする方法について説明します。
keywords: ユーザーの代理としてのアクセス、api、アプリケーション、ユーザー、アクセストークン、トークン、
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c3e5b758336f1a6ac57fcfcb448de93b7473591d
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650422"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a>ユーザーの代わりに Microsoft の脅威保護 Api にアクセスする

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


このページでは、ユーザーの代わりに Microsoft の脅威保護へのプログラムによるアクセスを得るためのアプリケーションを作成する方法について説明します。

ユーザーなしで Microsoft の脅威保護にプログラムにアクセスする必要がある場合は、「 [ユーザーなしで microsoft の脅威保護にアクセスするアプリを作成](api-create-app-web.md)する」を参照してください。

必要なアクセスが不明な場合は、「Microsoft の [脅威保護 api にアクセス](api-access.md)する」を参照してください。

Microsoft の脅威保護は、プログラム Api のセットを使用して、そのデータおよびアクションの多くを公開します。 これらの Api を使用すると、Microsoft の脅威保護機能に基づいて、作業フローとイノベーションを自動化できます。 API へのアクセスには、OAuth 2.0 認証が必要です。 詳細については、「 [OAuth 2.0 認証コードフロー](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)」を参照してください。

一般に、Api を使用するには、次の手順を実行する必要があります。
- AAD アプリケーションを作成する
- このアプリケーションを使用してアクセストークンを取得する
- トークンを使用して Microsoft の脅威保護 API にアクセスする

このページでは、AAD アプリケーションを作成する方法、Microsoft の脅威保護へのアクセストークンを取得する方法、トークンを検証する方法について説明します。

>[!NOTE]
> ユーザーに代わって Microsoft Threat Protection API にアクセスする場合は、適切なアプリケーションのアクセス許可とユーザーのアクセス許可が必要です。


>[!TIP]
> ポータルでアクションを実行するためのアクセス許可がある場合は、API でアクションを実行するためのアクセス許可があります。

## <a name="create-an-app"></a>アプリを作成する

1. **グローバル管理者**の役割を持つユーザーを使用して[Azure](https://portal.azure.com)にログオンします。

2. **Azure Active Directory**  >  **アプリ登録**  >  の**新しい登録**に移動します。 

   ![Microsoft Azure のイメージとアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. [登録元] で、次の情報を入力し、[ **登録**] をクリックします。

   ![アプリケーションの作成ウィンドウのイメージ](../../media/nativeapp-create2.PNG)

   - **Name:** アプリケーション名
   - **アプリケーションの種類:** パブリッククライアント
   - **リダイレクト URI:**https://portal.azure.com

4. アプリが Microsoft の脅威保護にアクセスできるようにして、it アクセス許可を割り当てるには、アプリケーションページで、[ **API アクセス**許可 api を追加する] [  >  **Add permission**  >  **組織は**> を使用します] を選択し、「 **microsoft threat protection**」と入力して、[ **microsoft threat protection**] を選択します。

    >[!NOTE]
    > Microsoft の脅威保護は、元のリストには表示されません。 テキストボックスに名前を記述して、表示されることを確認する必要があります。

      ![API アクセスと API 選択の画像](../../media/apis-in-my-org-tab.PNG)

    - [委任された **アクセス許可** ] を選択して、 **インシデント**などの該当するアクセス許可を選択し、[ **アクセス許可の追加**] を選択 > ます。

      ![API アクセスと API 選択の画像](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >関連するアクセス許可を選択する必要があります。 

    -  必要なアクセス許可を確認するには、呼び出したい API の [ **Permissions** ] セクションを参照してください。

    - [**同意を許可**する] をクリックする

      >[!NOTE]
      >アクセス許可を追加するたびに、新しいアクセス許可を有効にするには、[ **同意** を得る] をクリックする必要があります。

      ![許可権限の画像](../../media/grant-consent-delegated.PNG)

6. アプリケーション ID とテナント ID を書き留めておきます。

   - アプリケーションページで、[ **概要** ] に移動し、次の内容をコピーします。

   ![作成されたアプリ id の画像](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>PowerShell を使用してアクセストークンを取得する

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a>関連項目
- [Microsoft の脅威保護 Api にアクセスする](api-access.md)
- [アプリケーションコンテキストを使用して Microsoft の脅威保護にアクセスする](api-create-app-web.md)
