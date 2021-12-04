---
title: Microsoft Defender for Endpoint の接続アプリケーション
ms.reviewer: ''
description: 標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するためのトークンを提供する接続パートナー アプリケーションを表示します。
keywords: パートナー、アプリケーション、サードパーティ、接続、sentinelone、ルックアウト、bitdefender、corrata、morphisec、paloalto、ziften、より良いモバイル
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
ms.openlocfilehash: 4dd630dd2b35c2fedc0340cd873ff065b2685b41
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300648"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の接続アプリケーション

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

接続されたアプリケーションは、API を使用して Defender for Endpoint プラットフォームと統合されます。

アプリケーションは、標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するためのトークンを提供します。 さらに、Azure Active Directory (Azure AD) アプリケーションを使用すると、テナント管理者は、対応するアプリを使用してアクセスできる API を明示的に制御できます。

接続されているアプリケーションで API [を使用](/microsoft-365/security/defender-endpoint/apis-intro) するには、次の手順に従う必要があります。

左側のナビゲーション メニューから、[ **パートナー** ] を選択& API ([ **エンドポイント**] の下) >接続済み **アプリケーションです**。

## <a name="view-connected-application-details"></a>接続されているアプリケーションの詳細を表示する

[接続されたアプリケーション] ページには、組織内Azure AD Microsoft Defender for Endpoint に接続されているアプリケーションに関する情報が表示されます。 接続されているアプリケーションの使用状況を確認できます。前回の表示、過去 24 時間の要求数、過去 30 日間の傾向の要求を行います。

![接続されているアプリのイメージ。](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>接続されているアプリケーションの編集、再構成、または削除

[**アプリケーション設定を開く**] リンクは、Azure portal Azure AD対応するアプリケーション管理ページを開きます。 Azure portal から、接続されているアプリケーションのアクセス許可の管理、再構成、または削除を行います。
