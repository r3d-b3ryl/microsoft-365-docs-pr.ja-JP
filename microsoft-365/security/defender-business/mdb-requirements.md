---
title: Microsoft Defender for Businessの要件
description: Microsoft Defender for Businessライセンス、ハードウェア、ソフトウェアの要件
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ab24e3898d897df6813338fd0d2131c3787f0a09
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089586"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender for Business要件

この記事では、Microsoft Defender for Businessの要件について説明します。

## <a name="what-to-do"></a>操作

1. [要件を確認し、要件を満たしていることを確認します](#review-the-requirements)。
2. [次の手順に進みます](#next-steps)。


## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Microsoft Defender for Businessを構成して使用するための基本的な要件を示します。

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft 365 Business PremiumまたはMicrosoft Defender for Business (スタンドアロン)。 [Microsoft Defender for Businessを取得する方法に関する](get-defender-business.md)説明を参照してください。<br/><br/>複数のサブスクリプションがある場合は、最も高いサブスクリプションが優先されることに注意してください。 たとえば、プラン 2 Microsoft Defender for Endpoint (購入または試用版サブスクリプション) があり、Microsoft Defender for Businessを取得した場合、Defender for Endpoint プラン 2 が優先されます。 この場合、Defender for Business エクスペリエンスは表示されません。  |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |
| ユーザー アカウント | - ユーザー アカウントはMicrosoft 365 管理センターで作成されます ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>- Microsoft 365 管理センターでライセンスが割り当てられているMicrosoft Defender for Business<br/><br/>このタスクのヘルプについては、「ユーザーの [追加とライセンスの割り当て](mdb-add-users.md)」を参照してください。 |
| アクセス許可  | Microsoft Defender for Businessにサインアップするには、グローバル 管理である必要があります。<br/><br/>Microsoft 365 Defender ポータルにアクセスするには、[Azure AD で](mdb-roles-permissions.md)次のいずれかのロールが割り当てられている必要があります。 <br/>- セキュリティ リーダー<br/>- セキュリティ 管理<br/>- グローバル 管理<br/><br/>詳細については、「[Microsoft Defender for Businessのロールとアクセス許可](mdb-roles-permissions.md)」を参照してください。 |
| ブラウザー要件 | Microsoft Edgeまたは Google Chrome |
| オペレーティング システム | Microsoft 365 Defender ポータルでデバイスを管理するには、デバイスが次のいずれかのオペレーティング システムを実行している必要があります。 <br/>- Windows 10 Business 以降 <br/>- Windows 10 Professional 以降 <br/>- Windows 10 Enterprise 以降 <br/>- macOS (最新の 3 つのリリースがサポートされています)<br/><br/>WINDOWS デバイスに [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) がインストールされていることを確認します。 <br/><br/>Microsoft Intuneでデバイスを既に管理している場合は、Microsoft エンドポイント マネージャー管理センターを引き続き使用できます。 |

> [!NOTE]
> [Azure Active Directory (Azure AD)](/azure/active-directory/fundamentals/active-directory-whatis) は、ユーザーのアクセス許可とデバイス グループを管理するために使用されます。 Azure AD は Defender for Business サブスクリプションに含まれています。 
> - 試用版を開始する前にMicrosoft 365 サブスクリプションがない場合は、アクティブ化プロセス中に Azure AD がプロビジョニングされます。 
> - Defender for Business 試用版を開始するときに別のMicrosoft 365 サブスクリプションがある場合は、既存の Azure AD サービスを使用できます。 
> - Defender for Business 試用版を開始するときに[Microsoft 365 Business Premium](../../business/index.yml)を使用している場合は、Intuneを使用してデバイスを管理できます。 

## <a name="next-steps"></a>次の手順

[手順 2: Microsoft Defender for Businessでロールとアクセス許可を割り当てるに](mdb-roles-permissions.md)進みます。
 
