---
title: 脅威調査&対応機能 - Microsoft Defender for Office 365 プラン 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365プランの脅威調査と対応機能について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9d61da5a12882bef3ffee715bffb37ec96a18fd1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205878"
---
# <a name="threat-investigation-and-response"></a>脅威の調査および対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)


[Microsoft Defender](defender-for-office-365.md) for Office 365の脅威調査と対応機能は、セキュリティ アナリストと管理者が、次の方法で組織のMicrosoft 365を保護するのに役立ちます。

- サイバー攻撃の特定、監視、および理解を容易に行う
- オンライン、オンライン、オンライン、Exchange Online、SharePointの脅威に迅速OneDrive for Business対処Microsoft Teams
- セキュリティ操作が組織に対するサイバー攻撃を防ぐのに役立つ洞察と知識を提供する
- 電子メール[ベースの重大な脅威に対するOffice 365](automated-investigation-response-office.md)の自動調査と対応を採用する

脅威の調査と対応機能は、セキュリティ コンプライアンス センターで利用可能な脅威と関連する対応アクションに関する&提供します。 これらの分析情報は、組織のセキュリティ チームが電子メールまたはファイル ベースの攻撃からユーザーを保護するのに役立ちます。 この機能は、信号を監視し、ユーザーアクティビティ、認証、電子メール、侵害された PC、セキュリティ インシデントなど、複数のソースからのデータを収集するのに役立ちます。 ビジネス上の意思決定者とセキュリティ運用チームは、この情報を使用して、組織に対する脅威を理解し、対応し、知的財産を保護することができます。

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>脅威の調査と対応ツールについて知る

脅威の調査と対応機能は、次&含む一連のツールと対応ワークフローとして、セキュリティ コンプライアンス センターに表示されます。

- [脅威ダッシュボード](#threat-dashboard)
- [Explorer](#threat-explorer)
- [インシデント](#incidents)
- [攻撃シミュレータ](#attack-simulator)
- [自動調査および対応](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>脅威ダッシュボード

脅威ダッシュボード (これはセキュリティ ダッシュボードとも呼ばれます)[](security-dashboard.md)を使用して、対処された脅威をすばやく確認し、Microsoft 365 サービスがビジネスをセキュリティで保護している方法をビジネス意思決定者に視覚的に報告します。

![脅威ダッシュボード](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

このダッシュボードを表示して使用するには、セキュリティ &コンプライアンス センターで、[脅威管理ダッシュボード] **に移動** \> **します**。

### <a name="threat-explorer"></a>脅威エクスプローラー

脅威 [エクスプローラー (およびリアルタイム](threat-explorer.md) の検出) を使用して、脅威を分析し、時間の間に攻撃の量を確認し、脅威ファミリ、攻撃者インフラストラクチャなどによってデータを分析します。 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ アナリストの調査ワークフローの開始場所です。

![脅威エクスプローラー](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

このレポートを表示して使用するには、セキュリティ &コンプライアンス センターで、[脅威管理エクスプローラー] **に移動** \> **します**。

### <a name="incidents"></a>インシデント

フライト セキュリティ インシデントの一覧を表示するには、[インシデント] リスト (これは [調査] とも呼ばれる) を使用します。 インシデントは、疑わしい電子メール メッセージなどの脅威を追跡し、さらに調査と修復を行う場合に使用されます。

![現在の脅威インシデントの一覧 (Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

組織の現在のインシデントの一覧を表示するには、セキュリティ コンプライアンス センターで、[脅威&レビュー インシデント] に \>  \> **移動します**。

![セキュリティ コンプライアンス センターで&の管理レビューを選択 \> します。](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>攻撃シミュレーター

攻撃シミュレーターを使用して、組織内で現実的なサイバー攻撃を設定して実行し、実際のサイバー攻撃がビジネスに影響を与える前に脆弱なユーザーを特定します。 詳細については、「攻撃シミュレーター [」を参照Office 365。](attack-simulator.md)

### <a name="automated-investigation-and-response"></a>自動調査および対応

自動調査と応答 (AIR) 機能を使用して、組織内の脅威から危険にさらされているコンテンツ、デバイス、およびユーザーを関連付ける時間と労力を節約します。 AIR プロセスは、特定のアラートがトリガーされるたびに、またはセキュリティ運用チームによって開始されるたびに開始できます。 詳細については、「自動調査[と応答」を参照Office 365。](automated-investigation-response-office.md)

## <a name="threat-intelligence-widgets"></a>脅威インテリジェンス ウィジェット

Microsoft Defender for Office 365プラン 2 の提供の一環として、セキュリティ アナリストは既知の脅威に関する詳細を確認できます。 これは、ユーザーを安全に保つために実行できる追加の予防措置/手順が含まれるかどうかを判断する場合に役立ちます。

![最近の脅威に関する情報を示すセキュリティの傾向](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>これらの機能を取得する方法

Microsoft 365の脅威調査と対応機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして含まれる Office 365 プラン 2 の Microsoft Defender に含まれています。 詳細については[、「Defender for Office 365 1」および「Plan 2」を参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="required-roles-and-permissions"></a>必要な役割と権限

Microsoft Defender for Office 365ロール ベースのアクセス制御を使用します。 アクセス許可は、Azure Active Directory管理センター、Microsoft 365コンプライアンス センターの特定の役割&割り当てられます。

> [!TIP]
> セキュリティ管理者などの一部の役割はセキュリティ & コンプライアンス センターで割り当てることができますが、代わりに Microsoft 365 管理センターまたはセキュリティ Azure Active Directoryを使用Azure Active Directoryしてください。 役割、役割グループ、およびアクセス許可の詳細については、次のリソースを参照してください。
>
> - [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)
>
> - [Azure Active Directory での管理者役割のアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|アクティビティ|ロールと権限|
|---|---|
|脅威ダッシュボード (または新しいセキュリティ ダッシュボード[) を使用する](security-dashboard.md) <p> 最近または現在の脅威に関する情報を表示する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ リーダー**</li></ul> <p> これらの役割は、管理者センター ( ) または Azure Active Directory ( <https://portal.azure.com> ) でMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。|
|脅威 [エクスプローラー (およびリアルタイム検出) を使用して脅威](threat-explorer.md) を分析する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ リーダー**</li></ul> <p> これらの役割は、管理者センター ( ) または Azure Active Directory ( <https://portal.azure.com> ) でMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。|
|インシデントの表示 (調査とも呼ばれます) <p> インシデントへの電子メール メッセージの追加|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ リーダー**</li></ul> <p> これらの役割は、管理者センター ( ) または Azure Active Directory ( <https://portal.azure.com> ) でMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。|
|インシデントで電子メール アクションをトリガーする <p> 疑わしいメール メッセージの検索と削除|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者** と検索 **と削除の役割**</li></ul> <p> グローバル **管理者とセキュリティ****管理者の** 役割は、管理者 ( ) または管理者センター ( ) でAzure Active Directory割 <https://portal.azure.com> りMicrosoft 365割り当てることができます <https://admin.microsoft.com> 。 <p> 検索 **と削除の役割** は、セキュリティ コンプライアンス センター () &割り当てる必要があります <https://protection.office.com> 。|
|Microsoft Defender for Office 365プラン 2 と Microsoft Defender for Endpoint を統合する  <p> Microsoft Defender for Office 365プラン 2 を SIEM サーバーに統合する|[グローバル **管理者]** または[セキュリティ管理者] の役割が 、Azure Active Directory ( ) または管理者センター ( ) にMicrosoft 365 <https://portal.azure.com> 割り当てられます <https://admin.microsoft.com> 。 <p> --- **plus** --- <p> 追加のアプリケーションで割り当てられた適切な役割[](/windows/security/threat-protection/microsoft-defender-atp/user-roles)(Microsoft Defender セキュリティ センター SIEM サーバーなど)。|
|

## <a name="next-steps"></a>次の手順

- [脅威トラッカーの詳細 - 新機能と注目に値する](threat-trackers.md)

- [配信された悪意のある電子メールを検索して調査する (Office 365の調査と応答)](investigate-malicious-email-that-was-delivered.md)

- [脅威Office 365と対応を Microsoft Defender for Endpoint と統合する](integrate-office-365-ti-with-mde.md)

- [攻撃シミュレーターの詳細](attack-simulator.md)