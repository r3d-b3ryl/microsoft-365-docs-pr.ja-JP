---
title: ユーザーの要件Microsoft Defender for Business
description: Microsoft Defender for Business、ハードウェア、およびソフトウェアの要件
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 9fd082160640c239424ec75ff58c695a0175d630
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634935"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender for Business要件

> [!IMPORTANT]
> Microsoft Defender for Business 2022 年 3 月 1 [日](../../business-premium/index.md)からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

この記事では、ユーザーの要件についてMicrosoft Defender for Business。

## <a name="what-to-do"></a>操作

1. [要件を確認し、要件を満たしていることを確認します](#review-the-requirements)。

2. [次の手順に進みます](#next-steps)。

>
> **少し時間ありますか?**
> お問い合<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">わせに関する短いMicrosoft Defender for Business</a>。 ご意見をお寄せください。
>

## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、構成および使用する基本要件を示Microsoft Defender for Business。 <br/><br/>

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft 365 Business Premium <br/>--- または ---<br/>Microsoft Defender for Business (スタンドアロン、現在プレビュー中)。 <br/><br/> 詳細については[、「方法」を参照](get-defender-business.md)Microsoft Defender for Business。<br/><br/>複数のサブスクリプションがある場合は、最も高いサブスクリプションが優先されます。 たとえば、プラン 2 (購入Microsoft Defender for Endpoint試用版サブスクリプション) を使用している場合、エンドポイント プラン 2 のMicrosoft Defender for Business Defender が優先されます。 この場合、Defender for Business エクスペリエンスは表示されます。  |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |
| ユーザー アカウント | ユーザー アカウントは、ユーザー アカウント () Microsoft 365 管理センターに作成[https://admin.microsoft.com](https://admin.microsoft.com)されます。<br/><br/>Microsoft Defender for Businessライセンスが割り当てられているMicrosoft 365 管理センター<br/><br/>このタスクのヘルプについては、「ユーザーの追加とライセンス [の割り当て」を参照してください](../../admin/add-users/add-users.md)。 |
| アクセス許可  | アカウントにサインアップするには、Microsoft Defender for Business管理者である必要があります。<br/><br/>新しいポータルにMicrosoft 365 Defenderするには、ユーザーに割り当てられているアカウントで次[のいずれかのAzure AD](mdb-roles-permissions.md)必要があります。 <br/>- セキュリティ リーダー<br/>- セキュリティ管理者<br/>- グローバル管理者<br/><br/>詳細については、「ロールとアクセス許可」を参照[Microsoft Defender for Business](mdb-roles-permissions.md)。 |
| ブラウザー要件 | Microsoft Edgeまたは Google Chrome |
| オペレーティング システム | デバイスを管理するには、Microsoft Defender for Businessオペレーティング システムのいずれかを実行している必要があります。 <br/>- Windows 10 Business以降 <br/>- Windows 10 Professional以降 <br/>- Windows 10 Enterprise以降 <br/><br/>[KB5006738 がインストールされていることを](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)確認します。 <br/><br/>デバイスの管理が既に行Microsoft Intune (Microsoft エンドポイント マネージャー) の場合は、これらのデバイスを Defender for Business にオンボードできます。 |

> [!NOTE]
> [Azure Active Directory (Azure AD) を](/azure/active-directory/fundamentals/active-directory-whatis)使用して、ユーザーのアクセス許可とデバイス グループを管理します。 Azure AD Defender for Business サブスクリプションに含まれています。 
> - 試用版を開始する前Microsoft 365サブスクリプションをお持ちAzure ADライセンス認証プロセス中にプロビジョニングされます。 
> - Defender for Business 試用版をMicrosoft 365別のサブスクリプションがある場合は、既存のサブスクリプション サービスAzure ADできます。 
> - Defender for Business 試用版[Microsoft 365 Business Premium](../../business/index.yml)を使用している場合は、デバイスを管理するオプションがMicrosoft Intune。 

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 2: ロールとアクセス許可を割り当Microsoft Defender for Business](mdb-roles-permissions.md) 
 