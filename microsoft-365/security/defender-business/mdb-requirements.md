---
title: Microsoft Defender for Business の要件 (プレビュー)
description: Microsoft Defender for Business (プレビュー) ライセンス、ハードウェア、およびソフトウェア要件
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: b871288b836463918cdb2fa5a0bf50551010cdcf
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508325"
---
# <a name="microsoft-defender-for-business-preview-requirements"></a>Microsoft Defender for Business (プレビュー) の要件

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

この記事では、Microsoft Defender for Business (プレビュー) の要件について説明します。

## <a name="what-to-do"></a>操作

1. [要件を確認し、要件を満たしていることを確認します](#review-the-requirements)。

2. [次の手順に進みます](#next-steps)。

## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Microsoft Defender for Business (プレビュー) を構成して使用する基本的な要件を示します。 <br/><br/>

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft Defender for Business (現在プレビュー中!) 「 [ビジネス向け Microsoft Defender を取得する方法 (プレビュー)」を参照してください](get-defender-business.md)。<br/><br/>Microsoft Defender for Business (プレビュー)**を試Microsoft 365別** のサブスクリプションを持っている必要はありません。 |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |
| ユーザー アカウント | ユーザー アカウントが作成される<br/><br/>Microsoft Defender for Business (プレビュー) ライセンスが割り当てられている <br/><br/>このヘルプについては、「ユーザーの追加とライセンス [の割り当て」を参照してください](../../admin/add-users/add-users.md)。 |
| アクセス許可  | Microsoft Defender for Business (プレビュー) にサインアップするには、グローバル管理者である必要があります。<br/><br/>このポータルにMicrosoft 365 Defenderするには、ユーザーが割り当てられているアカウントで次[のいずれかのAzure AD](mdb-roles-permissions.md)必要があります。 <br/>- セキュリティ リーダー<br/>- セキュリティ管理者<br/>- グローバル管理者<br/><br/>詳細については、「Microsoft Defender for Business (プレビュー) [の役割とアクセス許可」を参照してください](mdb-roles-permissions.md)。 |
| ブラウザー要件 | Microsoft Edgeまたは Google Chrome |
| オペレーティング システム | Microsoft Defender for Business (プレビュー) でデバイスを管理するには、デバイスが Windows 10 Professional/Enterprise 以降[(KB5006738)](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)で実行されている必要があります。 <br/><br/>Microsoft Intune (または Microsoft エンドポイント マネージャー) でデバイスを既に管理している場合、または Microsoft 以外のデバイス管理ソリューションを使用している場合は[、Microsoft Defender for Endpoint](../defender-endpoint/minimum-requirements.md)でサポートされているオペレーティング システムの 1 つをデバイスで実行している必要があります。 |
| アプリケーションとのMicrosoft エンドポイント マネージャー  |  **プレビュー中は、ローカル スクリプトを使用して** デバイスをオンボードできます。ローカル スクリプトとの統合はMicrosoft エンドポイント マネージャー。 ただし、Microsoft エンドポイント マネージャー、グループ ポリシー、System Center Configuration Manager、またはモバイル デバイス管理にダウンロード可能なパッケージを使用して、デバイスを Defender for Business (プレビュー) に手動でオンボードする場合は、次の要件を満たす必要があります。 <br/><br/>デバイスは、KB5006738 Windows 10または 11 Professional/Enterprise [(KB5006738)](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)で実行されている必要があります。 <br/><br/>Microsoft Defender for Endpoint のセキュリティ管理の前提条件 [を満たす必要があります](/mem/intune/protect/mde-security-integration)。<br/>- Azure AD、会社のデバイスとデバイス間で信頼が作成Azure AD。 <br/>- Defender for Business (プレビュー) では、セキュリティ管理が有効になっている必要Microsoft エンドポイント マネージャー。<br/><br/>デバイスは、次の URL に接続できる必要があります。<br/>- `enterpriseregistration.windows.net`(Azure AD)<br/>- `login.microsoftonline.com`(Azure AD)<br/>- `*.dm.microsoft.com` (ワイルドカード (*) は、登録、チェックイン、およびレポートに使用されるクラウド サービス エンドポイントをサポートし、サービスの規模に応じ変更できます)。 |

> [!NOTE]
> [Azure Active Directory (Azure AD) を](/azure/active-directory/fundamentals/active-directory-whatis)使用して、ユーザーのアクセス許可とデバイス グループを管理します。 Azure AD Defender for Business (プレビュー) サブスクリプションに含まれています。 
> - 試用版を開始する前Microsoft 365サブスクリプションをお持ちAzure ADライセンス認証プロセス中にプロビジョニングされます。 
> - Defender for Business (プレビュー) 試用版Microsoft 365別のサブスクリプションがある場合は、既存のサービスをAzure ADできます。 
> - Defender for Business (プレビュー) [Microsoft 365 Business Premium](../../business/index.yml)を開始するときにアプリを使用している場合は、アプリ内のデバイスを管理Microsoft Intune。 

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 2: Microsoft Defender for Business で役割とアクセス許可を割り当てる (プレビュー)](mdb-roles-permissions.md) 
 