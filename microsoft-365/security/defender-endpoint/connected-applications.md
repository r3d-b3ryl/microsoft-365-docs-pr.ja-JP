---
title: Microsoft Defender for Endpointの接続済みアプリケーション
ms.reviewer: ''
description: 標準 OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するトークンを提供する接続済みパートナー アプリケーションを表示します。
keywords: パートナー, アプリケーション, サード パーティ, 接続, sentinelone, Lookout, bitdefender, corrata, morphisec, paloalto, ziften, Better mobile
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9e15103f4366d0717af9cec44d516b4b16a7160a
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475567"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointの接続済みアプリケーション

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

接続されたアプリケーションは、API を使用して Defender for Endpoint プラットフォームと統合されます。

アプリケーションでは、標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するトークンを提供します。 さらに、Azure Active Directory (Azure AD) アプリケーションを使用すると、テナント管理者は、対応するアプリを使用してアクセスできる API を明示的に制御できます。

接続されたアプリケーションで API を使用するには、 [次の手順](/microsoft-365/security/defender-endpoint/apis-intro) に従う必要があります。

左側のナビゲーション メニューから、(**[エンドポイント**] の下にある ) [**パートナー & API**] > **[接続済みアプリケーション**] を選択します。

## <a name="view-connected-application-details"></a>接続されているアプリケーションの詳細を表示する

[接続済みアプリケーション] ページには、組織内のMicrosoft Defender for Endpointに接続されているAzure AD アプリケーションに関する情報が表示されます。 接続されたアプリケーションの使用状況 (前回表示された回数、過去 24 時間の要求数、過去 30 日間の要求の傾向) を確認できます。

:::image type="content" source="images/connected-apps.png" alt-text="接続されているアプリケーション" lightbox="images/connected-apps.png":::
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>接続されているアプリケーションを編集、再構成、または削除する

[**アプリケーション設定を開く]** リンクをクリックすると、Azure portalで対応するAzure ADアプリケーション管理ページが開きます。 Azure portalから、接続されているアプリケーションのアクセス許可の管理、再構成、または削除を行うことができます。
