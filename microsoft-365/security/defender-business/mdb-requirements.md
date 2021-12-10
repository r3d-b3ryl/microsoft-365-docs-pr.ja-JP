---
title: Microsoft Defender for Business の要件
description: Microsoft Defender for Business ライセンス、ハードウェア、およびソフトウェアの要件
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 43ff9e7957e5ec26f3242266c8393bdefdb3240f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375453"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender for Business の要件

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

この記事では、Microsoft Defender for Business の要件について説明します。

## <a name="what-to-do"></a>操作

1. [要件を確認し、要件を満たしていることを確認します](#review-the-requirements)。

2. [次の手順に進みます](#next-steps)。

## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Microsoft Defender for Business を構成して使用する基本的な要件を示します。 <br/><br/>

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft Defender for Business (現在プレビュー中!) 「 [ビジネス向け Microsoft Defender を取得する方法」を参照してください](get-defender-business.md)。<br/><br/>Microsoft Defender for Business を試Microsoft 365別のサブスクリプションを持っている必要はありません。 |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |
| Azure Active Directory (Azure AD) | Azure ADアクセス許可とデバイス グループに対して必須です。 Azure AD Defender for Business サブスクリプションに含まれています。 詳細については、「What [is is Azure AD?](/azure/active-directory/fundamentals/active-directory-whatis) |
| ユーザー アカウント | ユーザー アカウントが作成される<br/><br/>Microsoft Defender for Business ライセンスが割り当てられている <br/><br/>このヘルプについては、「ユーザーの追加とライセンス [の割り当て」を参照してください](../../admin/add-users/add-users.md)。 |
| アクセス許可  | このポータルにMicrosoft 365 Defenderするには、ユーザーが割り当てられているアカウントで次[のいずれかのAzure AD](mdb-roles-permissions.md)必要があります。 <br/>- セキュリティ リーダー<br/>- セキュリティ管理者<br/>- グローバル管理者<br/><br/>詳細については [、「Microsoft Defender for Business の役割とアクセス許可」を参照してください](mdb-roles-permissions.md)。 |
| ブラウザー要件 | Microsoft Edgeまたは Google Chrome |
| オペレーティング システム | Microsoft Defender for Business でデバイスを管理するには、デバイスが Windows 10 Professional/Enterprise以降[(KB5006738) で実行されている必要があります](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)。 <br/><br/>Microsoft Intune (または Microsoft エンドポイント マネージャー) でデバイスを既に管理している場合、または Microsoft 以外のデバイス管理ソリューションを使用している場合は[、Microsoft Defender for Endpoint](../defender-endpoint/minimum-requirements.md)でサポートされているオペレーティング システムの 1 つをデバイスで実行している必要があります。 |
| アプリケーションとのMicrosoft エンドポイント マネージャー  |  **プレビュー中は、ローカル スクリプトを使用してデバイスをオンボードできます。この場合、ここに記載されているMicrosoft エンドポイント マネージャーとの統合の前提条件は必要ありません**。 ただし、Microsoft エンドポイント マネージャー、グループ ポリシー、System Center Configuration Manager、またはモバイル デバイス管理用のダウンロード可能なパッケージを使用してデバイスを Defender for Business に手動でオンボードする場合は、次の要件を満たす必要があります。 <br/><br/>デバイスは、KB5006738 Windows 10または 11 Professional/Enterprise [(KB5006738)](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)で実行されている必要があります。 <br/><br/>Microsoft Defender for Endpoint のセキュリティ管理の前提条件 [を満たす必要があります](/mem/intune/protect/mde-security-integration)。<br/>- Azure AD、会社のデバイスとデバイス間で信頼が作成Azure AD。 <br/>- Defender for Business では、セキュリティ管理が有効になっている必要Microsoft エンドポイント マネージャー。<br/><br/>デバイスは、次の URL に接続できる必要があります。<br/>- `enterpriseregistration.windows.net`(Azure AD)<br/>- `login.microsoftonline.com`(Azure AD)<br/>- `*.dm.microsoft.com` (ワイルドカード (*) は、登録、チェックイン、およびレポートに使用されるクラウド サービス エンドポイントをサポートし、サービスの規模に応じ変更できます)。 |


## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 2: Microsoft Defender for Business で役割とアクセス許可を割り当てる](mdb-roles-permissions.md) 
 