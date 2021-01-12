---
title: 脅威の調査&対応機能 - Microsoft Defender for Office 365 プラン 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
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
description: Microsoft Defender for Office 365 プランの脅威の調査と対応の機能について説明します。
ms.openlocfilehash: dc6a3dec096b6834d024cc4ff74a5b7600c33d45
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794234"
---
# <a name="threat-investigation-and-response"></a>脅威の調査および対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365](office-365-atp.md)向け Microsoft Defender の脅威の調査および対応機能は、セキュリティ アナリストと管理者が次の方法で組織のビジネス ユーザー向け Microsoft 365 を保護するのに役立ちます。

- サイバー攻撃の特定、監視、および理解を容易に
- Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teams の脅威に迅速に対処する
- セキュリティ運用が組織に対するサイバー攻撃を防ぐのに役立つ洞察と知識を提供する
- 電子メール [ベースの重要な脅威に対する Office 365 での](automated-investigation-response-office.md) 自動調査と対応の採用

脅威の調査と対応の機能は、セキュリティ/コンプライアンス センターで利用可能な脅威と関連する対応アクション&提供します。 これらの分析情報は、組織のセキュリティ チームが電子メールまたはファイル ベースの攻撃からユーザーを保護するのに役立ちます。 この機能は、ユーザーアクティビティ、認証、電子メール、侵害された PC、セキュリティ インシデントなど、シグナルを監視し、複数のソースからデータを収集するのに役立ちます。 ビジネス意思決定者とセキュリティ運用チームは、この情報を使用して、組織に対する脅威を理解して対応し、知的財産を保護することができます。

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>脅威の調査と対応のツールについて知る

脅威の調査と対応の機能は、セキュリティ & コンプライアンス センターに、次のような一連のツールと対応ワークフローとして表示されます。

- [脅威ダッシュボード](#threat-dashboard)
- [Explorer](#threat-explorer)
- [インシデント](#incidents)
- [攻撃シミュレータ](#attack-simulator)
- [自動調査および対応](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>脅威ダッシュボード

脅威ダッシュボード (これはセキュリティ ダッシュボードとも呼 [ばれます)](security-dashboard.md)を使用して、対処された脅威をすばやく確認し、Microsoft 365 サービスがビジネスをセキュリティで保護している方法をビジネスの意思決定者に視覚的に報告する方法として使用します。

![脅威ダッシュボード](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)

このダッシュボードを表示して使用するには、セキュリティ & コンプライアンス センターで、脅威管理 **ダッシュボードに移動** \> **します**。

### <a name="threat-explorer"></a>脅威エクスプローラー

脅威 [エクスプローラー (および](threat-explorer.md) リアルタイムの検出) を使用して、脅威の分析、時間の中での攻撃の量の確認、脅威ファミリや攻撃者のインフラストラクチャなどのデータの分析を行います。 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ アナリストの調査ワークフローの開始場所です。

![脅威エクスプローラー](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)

このレポートを表示して使用するには、セキュリティ & コンプライアンス センターで、脅威管理 **エクスプローラーに移動** \> **します**。

### <a name="incidents"></a>インシデント

インシデント リスト (これは調査とも呼ばれる) を使用して、フライト中のセキュリティ インシデントの一覧を表示します。 インシデントは、疑わしい電子メール メッセージなどの脅威を追跡し、さらに調査と修復を行うのに使用されます。

![Office 365 の現在の脅威インシデントのリスト](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)

組織の現在のインシデントの一覧を表示するには、セキュリティ/コンプライアンス センターで、[脅威&レビュー インシデント] に \>  \> **移動します**。

![セキュリティ/コンプライアンス センターで&管理レビューを選択 \> します。](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>攻撃シミュレータ

攻撃シミュレータを使用して、組織で現実的なサイバー攻撃を設定して実行し、実際のサイバー攻撃がビジネスに影響を与える前に脆弱なユーザーを特定します。 詳細については、「Office [365」を参照](attack-simulator.md)してください。

### <a name="automated-investigation-and-response"></a>自動調査および対応

自動調査および対応 (AIR) 機能を使用して、組織内の脅威から危険にさらされているコンテンツ、デバイス、およびユーザーを関連付ける時間と労力を節約します。 AIR プロセスは、特定のアラートがトリガーされた場合や、セキュリティ運用チームによって開始された場合に開始できます。 詳細については、Office [365 での自動調査と対応を参照](automated-investigation-response-office.md)してください。

## <a name="threat-intelligence-widgets"></a>脅威インテリジェンス ウィジェット

Microsoft Defender for Office 365 プラン 2 サービスの一部として、セキュリティ アナリストは既知の脅威に関する詳細を確認できます。 これは、ユーザーの安全を確保するために実行できる追加の予防手段/手順が含まれるかどうかを判断する場合に役立ちます。

![最近の脅威に関する情報を示すセキュリティの傾向](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png)

## <a name="how-do-we-get-these-capabilities"></a>これらの機能を取得する方法

Microsoft 365 脅威の調査および対応機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして含まれる Office 365 プラン 2 の Microsoft Defender に含まれています。 詳細については [、「Defender for Office 365 プラン 1 およびプラン 2」を参照してください](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="required-roles-and-permissions"></a>必要な役割と権限

Microsoft Defender for Office 365 は、役割ベースのアクセス制御を使用します。 アクセス許可は、Azure Active Directory、Microsoft 365 管理センター、またはセキュリティ/コンプライアンス センターの特定のロール&割り当てられます。

> [!TIP]
> セキュリティ管理者などの一部の役割はセキュリティ & コンプライアンス センターで割り当てることができますが、代わりに Microsoft 365 管理センターまたは Azure Active Directory の使用を検討してください。 役割、役割グループ、およびアクセス許可の詳細については、次のリソースを参照してください。
>
> - [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)
>
> - [Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

****

|アクティビティ|ロールと権限|
|---|---|
|脅威ダッシュボード (または新しいセキュリティ ダッシュボード)[を使用する](security-dashboard.md) <p> 最近または現在の脅威に関する情報を表示する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ閲覧者**</li></ul> <p> これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。|
|脅威 [エクスプローラー (およびリアルタイムの検出) を使用して](threat-explorer.md) 脅威を分析する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ閲覧者**</li></ul> <p> これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。|
|インシデントの表示 (調査とも呼ばれます) <p> インシデントに電子メール メッセージを追加する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ閲覧者**</li></ul> <p> これらの役割は、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。|
|インシデントでメール アクションをトリガーする <p> 不審な電子メール メッセージを検索して削除する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者** と **"Search and Purge/検索と消去" 役割**</li></ul> <p> グローバル **管理者ロールと****セキュリティ** 管理者ロールは、Azure Active Directory ( ) または <https://portal.azure.com> Microsoft 365 管理センター ( ) で割り当てることができます <https://admin.microsoft.com> 。 <p> Search **and Purge 役割は** 、セキュリティ/コンプライアンス センター () &割り当てられている必要があります <https://protection.office.com> 。|
|Microsoft Defender for Office 365 プラン 2 と Microsoft Defender for Endpoint の統合  <p> Microsoft Defender for Office 365 プラン 2 と SIEM サーバーの統合|Azure  Active Directory  ( ) または Microsoft 365 管理センター ( ) で割り当てられたグローバル管理者または <https://portal.azure.com> セキュリティ管理者の役割のいずれか <https://admin.microsoft.com> 。 <p> --- **plus** --- <p> 追加のアプリケーション [(Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) セキュリティ センターや SIEM サーバーなど) で割り当てられた適切な役割。|
|

## <a name="next-steps"></a>次の手順

- [脅威トラッカーの詳細 - 新機能と注目すべき機能](threat-trackers.md)

- [配信された悪意のあるメールを検索して調査する (Office 365 脅威の調査と対応)](investigate-malicious-email-that-was-delivered.md)

- [Office 365 脅威の調査と対応を Microsoft Defender for Endpoint と統合する](integrate-office-365-ti-with-wdatp.md)

- [攻撃シミュレータの詳細](attack-simulator.md)
