---
title: Microsoft Defender for Endpoint の接続アプリケーション
ms.reviewer: ''
description: 標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するためのトークンを提供する接続パートナー アプリケーションを表示します。
keywords: パートナー、アプリケーション、サードパーティ、接続、sentinelone、ルックアウト、bitdefender、corrata、morphisec、paloalto、ziften、より良いモバイル
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845584"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint の接続アプリケーション

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

接続されたアプリケーションは、API を使用して Defender for Endpoint プラットフォームと統合されます。 

アプリケーションは、標準の OAuth 2.0 プロトコルを使用して認証を行い、Microsoft Defender for Endpoint API で使用するためのトークンを提供します。  さらに、Azure Active Directory (Azure AD) アプリケーションを使用すると、テナント管理者は、対応するアプリを使用してアクセスできる API を明示的に制御できます。
 
接続されているアプリケーションで API [を使用](/microsoft-365/security/defender-endpoint/apis-intro) するには、次の手順に従う必要があります。
 
## <a name="access-the-connected-application-page"></a>接続されているアプリケーション ページにアクセスする
左側のナビゲーション メニューで、[**パートナー] を選択&接続**  >  **された AAD アプリケーションを選択します**。

 
## <a name="view-connected-application-details"></a>接続されているアプリケーションの詳細を表示する
[接続されたアプリケーション] ページには、組織内の Microsoft Defender for Endpoint に接続AD Azure アプリケーションに関する情報が表示されます。 接続されているアプリケーションの使用状況を確認できます。前回の表示、過去 24 時間の要求数、過去 30 日間の傾向の要求を行います。

![接続されているアプリの画像](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>接続されているアプリケーションの編集、再構成、または削除
[ **アプリケーションの設定を開** く] リンクをクリックすると、対応する Azure ADアプリケーション管理ページが Azure portal で開きます。 Azure portal から、接続されているアプリケーションのアクセス許可の管理、再構成、または削除を行います。
