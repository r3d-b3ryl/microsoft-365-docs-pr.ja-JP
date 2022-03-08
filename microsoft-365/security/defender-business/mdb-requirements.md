---
title: Microsoft Defender for Business の要件
description: Microsoft Defender for Business ライセンス、ハードウェア、およびソフトウェアの要件
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 1f8364cc46800f5631ac9919a8f59415b35005a3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313063"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender for Business の要件

> [!IMPORTANT]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

この記事では、Microsoft Defender for Business の要件について説明します。

## <a name="what-to-do"></a>操作

1. [要件を確認し、要件を満たしていることを確認します](#review-the-requirements)。

2. [次の手順に進みます](#next-steps)。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business に関する短いアンケートをご覧ください</a>。 ご意見をお寄せください。
>

## <a name="review-the-requirements"></a>システム要件を確認する

次の表に、Microsoft Defender for Business を構成して使用する基本的な要件を示します。 <br/><br/>

| 要件 | 説明 |
|:---|:---|
| サブスクリプション | Microsoft 365 Business Premium <br/>--- または ---<br/>Microsoft Defender for Business (スタンドアロン、現在プレビュー中)。 <br/><br/> 「 [ビジネス向け Microsoft Defender を取得する方法」を参照してください](get-defender-business.md)。<br/><br/>複数のサブスクリプションがある場合は、最も高いサブスクリプションが優先されます。 たとえば、Microsoft Defender for Endpoint Plan 2 (購入または試用版サブスクリプション) を持ち、Microsoft Defender for Business を取得した場合、Defender for Endpoint Plan 2 が優先されます。 この場合、Defender for Business エクスペリエンスは表示されます。  |
| Datacenter | 次のいずれかのデータセンターの場所。 <br/>- 欧州連合 <br/>- イギリス <br/>- 米国 |
| ユーザー アカウント | ユーザー アカウントは、ユーザー アカウント () Microsoft 365 管理センターに作成[https://admin.microsoft.com](https://admin.microsoft.com)されます。<br/><br/>Microsoft Defender for Business のライセンスは、ユーザーに割り当Microsoft 365 管理センター<br/><br/>このタスクのヘルプについては、「ユーザーの追加とライセンス [の割り当て」を参照してください](../../admin/add-users/add-users.md)。 |
| アクセス許可  | Microsoft Defender for Business にサインアップするには、グローバル管理者である必要があります。<br/><br/>新しいポータルにMicrosoft 365 Defenderするには、ユーザーに割り当てられているアカウントで次[のいずれかのAzure AD](mdb-roles-permissions.md)必要があります。 <br/>- セキュリティ リーダー<br/>- セキュリティ管理者<br/>- グローバル管理者<br/><br/>詳細については、「 [Microsoft Defender for Business のロールとアクセス許可」を参照してください](mdb-roles-permissions.md)。 |
| ブラウザー要件 | Microsoft Edgeまたは Google Chrome |
| オペレーティング システム | Microsoft Defender for Business でデバイスを管理するには、デバイスで次のいずれかのオペレーティング システムを実行している必要があります。 <br/>- Windows 10 Business以降 <br/>- Windows 10 Professional以降 <br/>- Windows 10 Enterprise以降 <br/><br/>[KB5006738 がインストールされていることを](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)確認します。 <br/><br/>Microsoft Intune (または Microsoft エンドポイント マネージャー) でデバイスを既に管理している場合、または Microsoft 以外のデバイス管理ソリューションを使用している場合は、[Microsoft Defender for Endpoint](../defender-endpoint/minimum-requirements.md) でサポートされているオペレーティング システムの 1 つがデバイスで実行されている必要があります。 |
| ユーザーとのMicrosoft エンドポイント マネージャー  | [Microsoft Defender for Business](mdb-onboard-devices.md#microsoft-defender-for-business-security-configuration) セキュリティ構成を使用してデバイスをオンボードする場合は、次の要件を満たす必要があります。<br/><br/>Microsoft [Defender for Endpoint のセキュリティ管理の前提条件を満たす必要があります](/mem/intune/protect/mde-security-integration)。<br/>- Azure ADのデバイスと組織のデバイス間で信頼を作成するように構成する必要Azure AD。 <br/>- Defender for Business では、セキュリティ管理が有効になっている必要Microsoft エンドポイント マネージャー。<br/><br/>デバイスは、次の URL に接続できる必要があります。<br/>- `enterpriseregistration.windows.net`(Azure AD)<br/>- `login.microsoftonline.com`(Azure AD)<br/>- `*.dm.microsoft.com` (ワイルドカード (*) は、登録、チェックイン、およびレポートに使用されるクラウド サービス エンドポイントをサポートし、サービスの規模に応じ変更できます)。 |

> [!NOTE]
> [Azure Active Directory (Azure AD) を](/azure/active-directory/fundamentals/active-directory-whatis)使用して、ユーザーのアクセス許可とデバイス グループを管理します。 Azure AD Defender for Business サブスクリプションに含まれています。 
> - 試用版を開始する前Microsoft 365サブスクリプションをお持ちAzure ADライセンス認証プロセス中にプロビジョニングされます。 
> - Defender for Business 試用版をMicrosoft 365別のサブスクリプションがある場合は、既存のサブスクリプション サービスAzure ADできます。 
> - Defender for Business 試用版[Microsoft 365 Business Premium](../../business/index.yml)を使用している場合は、デバイスを管理するオプションがMicrosoft Intune。 

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 2: Microsoft Defender for Business で役割とアクセス許可を割り当てる](mdb-roles-permissions.md) 
 