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
ms.localizationpriority: medium
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c972a42730f4d21b73227a8b8a9900223109d590
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972037"
---
# <a name="threat-investigation-and-response"></a>脅威の調査および対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)の脅威の調査と対応機能は、セキュリティ アナリストと管理者が、ビジネス ユーザーに対する組織のMicrosoft 365を次の方法で保護するのに役立ちます。

- サイバー攻撃を簡単に識別、監視、理解できるようにします。
- Exchange Online、SharePoint Online、OneDrive for Business、Microsoft Teamsの脅威に迅速に対処するのに役立ちます。
- セキュリティ運用が組織に対するサイバー攻撃を防ぐのに役立つ分析情報と知識を提供する。
- 重要な電子メール ベースの脅威[に対して、Office 365での自動調査と対応](automated-investigation-response-office.md)を採用しています。

脅威の調査と対応機能は、Microsoft 365 Defender ポータルで利用できる脅威と関連する対応アクションに関する分析情報を提供します。 これらの分析情報は、組織のセキュリティ チームが電子メールまたはファイルベースの攻撃からユーザーを保護するのに役立ちます。 この機能は、シグナルを監視し、ユーザー アクティビティ、認証、電子メール、侵害された PC、セキュリティ インシデントなど、複数のソースからデータを収集するのに役立ちます。 ビジネス意思決定者とセキュリティ運用チームは、この情報を使用して、組織に対する脅威を理解して対応し、知的財産を保護することができます。

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>脅威の調査と対応ツールについて知る

Microsoft 365 Defender ポータル<https://security.microsoft.com>の脅威の調査と対応機能は、次のようなツールと応答ワークフローのセットです。

- [Explorer](#explorer)
- [インシデント](#incidents)
- [攻撃シミュレーション トレーニング](attack-simulation-training.md)
- [自動調査および対応](automated-investigation-response-office.md)

### <a name="explorer"></a>エクスプローラー

[エクスプローラー (およびリアルタイム検出)](threat-explorer.md) を使用して、脅威を分析し、時間の経過に伴う攻撃の量を確認し、脅威ファミリ、攻撃者インフラストラクチャなどのデータを分析します。 エクスプローラー (脅威エクスプローラーとも呼ばれます) は、セキュリティ アナリストの調査ワークフローの出発点です。

:::image type="content" source="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png" alt-text="脅威エクスプローラー ページ" lightbox="../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png":::

Microsoft 365 Defender ポータル<https://security.microsoft.com>でこのレポートを表示して使用するには、**電子メール & コラボレーション** \> エクスプローラーに移動 **します**。 または、 **エクスプローラー** ページに直接移動するには、 <https://security.microsoft.com/threatexplorer>.

## <a name="office-365-threat-intelligence-connection"></a>Office 365脅威インテリジェンス接続

この機能は、アクティブなOffice 365 E5 サブスクリプションまたは脅威インテリジェンス アドオンがある場合にのみ使用できます。 詳細については、Office 365 Enterprise E5 製品ページを参照してください。

この機能を有効にすると、Microsoft Defender for Office 365のデータをMicrosoft 365 Defenderに組み込み、Office 365 メールボックスとWindows デバイス全体で包括的なセキュリティ調査を行うことができます。

> [!NOTE]
> この機能を有効にするには、適切なライセンスが必要です。

Office 365脅威インテリジェンスでコンテキスト に応じたデバイス統合を受け取るには、セキュリティ & コンプライアンス ダッシュボードで Defender for Endpoint の設定を有効にする必要があります。

### <a name="incidents"></a>インシデント

インシデントの一覧 (これは "調査" とも呼ばれます) を使用して、フライト内のセキュリティ インシデントの一覧を表示します。 インシデントは、疑わしい電子メール メッセージなどの脅威を追跡し、さらに調査と修復を行うために使用されます。

:::image type="content" source="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png" alt-text="Office 365の現在の脅威インシデントの一覧" lightbox="../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png":::

Microsoft 365 Defender ポータル<https://security.microsoft.com>で組織の現在のインシデントの一覧を表示するには、**インシデント&アラート** \> **インシデント** に移動します。 または、[ **インシデント]** ページに直接移動するには、 <https://security.microsoft.com/incidents>.

:::image type="content" source="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png" alt-text="セキュリティ & コンプライアンス センターの [校閲] ページ" lightbox="../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png":::

### <a name="attack-simulation-training"></a>攻撃シミュレーション トレーニング

攻撃シミュレーション トレーニングを使用して、組織内で現実的なサイバー攻撃を設定して実行し、実際のサイバー攻撃がビジネスに影響を与える前に脆弱なユーザーを特定します。 詳細については、「 [フィッシング攻撃をシミュレートする](attack-simulation-training.md)」を参照してください。

Microsoft 365 Defender ポータルで<https://security.microsoft.com>この機能を表示して使用するには、**email & collaborationAttack** >  **シミュレーション トレーニング** に移動します。 または、 **攻撃シミュレーションのトレーニング** ページに直接移動するには、 <https://security.microsoft.com/attacksimulator?viewid=overview>.

### <a name="automated-investigation-and-response"></a>自動調査および対応

自動調査と対応 (AIR) 機能を使用して、組織内の脅威の危険にさらされているコンテンツ、デバイス、人を関連付ける時間と労力を節約します。 AIR プロセスは、特定のアラートがトリガーされたとき、またはセキュリティ運用チームによって開始されるたびに開始できます。 詳細については、[Office 365の自動調査と対応に](automated-investigation-response-office.md)関するページを参照してください。

## <a name="threat-intelligence-widgets"></a>脅威インテリジェンス ウィジェット

Microsoft Defender for Office 365プラン 2 オファリングの一環として、セキュリティ アナリストは既知の脅威に関する詳細を確認できます。 これは、ユーザーを安全に保つために実行できる追加の予防措置/手順があるかどうかを判断するのに役立ちます。

:::image type="content" source="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png" alt-text="最近の脅威に関する情報を示す [セキュリティの傾向] ウィンドウ" lightbox="../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png":::

## <a name="how-do-we-get-these-capabilities"></a>これらの機能を入手するにはどうすればよいですか?

Microsoft 365脅威の調査と対応機能は、Enterprise E5 または特定のサブスクリプションのアドオンとして含まれるMicrosoft Defender for Office 365プラン 2 に含まれています。 詳細については、「[Defender for Office 365 プラン 1 とプラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)」を参照してください。

## <a name="required-roles-and-permissions"></a>必要な役割と権限

Microsoft Defender for Office 365では、ロールベースのアクセス制御が使用されます。 アクセス許可は、Azure Active Directory、Microsoft 365 管理センター、またはMicrosoft 365 Defender ポータルの特定のロールを介して割り当てられます。

> [!TIP]
> セキュリティ管理者などの一部のロールはMicrosoft 365 Defender ポータルで割り当てることができますが、代わりにMicrosoft 365 管理センターまたはAzure Active Directoryのいずれかを使用することを検討してください。 ロール、ロール グループ、アクセス許可の詳細については、次のリソースを参照してください。
>
> - [Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)
> - [組み込みロールをAzure ADする](/azure/active-directory/roles/permissions-reference)

|アクティビティ|ロールと権限|
|---|---|
|脅威&脆弱性管理ダッシュボード (または新しい[セキュリティ ダッシュボード](security-dashboard.md)) を使用する <p> 最近の脅威または現在の脅威に関する情報を表示する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ閲覧者**</li></ul> <p> これらのロールは、Azure Active Directory () またはMicrosoft 365 管理センター (<https://portal.azure.com><https://admin.microsoft.com>) のいずれかで割り当てることができます。|
|[エクスプローラー (およびリアルタイム検出)](threat-explorer.md) を使用して脅威を分析する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ閲覧者**</li></ul> <p> これらのロールは、Azure Active Directory () またはMicrosoft 365 管理センター (<https://portal.azure.com><https://admin.microsoft.com>) のいずれかで割り当てることができます。|
|インシデントの表示 ("調査" とも呼ばれます) <p> インシデントに電子メール メッセージを追加する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者**</li><li>**セキュリティ閲覧者**</li></ul> <p> これらのロールは、Azure Active Directory () またはMicrosoft 365 管理センター (<https://portal.azure.com><https://admin.microsoft.com>) のいずれかで割り当てることができます。|
|インシデントで電子メール アクションをトリガーする <p> 疑わしい電子メール メッセージを検索して削除する|以下のいずれか: <ul><li>**グローバル管理者**</li><li>**セキュリティ管理者** と **検索ロールと消去** ロール</li></ul> <p> **グローバル管理者** ロールと **セキュリティ管理者** ロールは、Azure Active Directory () または Microsoft 365 管理センター (<https://portal.azure.com><https://admin.microsoft.com>) で割り当てることができます。 <p> **検索ロールと消去** ロールは、Microsoft 36 Defender ポータル (<https://security.microsoft.com>) の **電子メール & コラボレーション ロール** で割り当てる必要があります。|
|Microsoft Defender for Office 365プラン 2 とMicrosoft Defender for Endpointを統合する <p> Microsoft Defender for Office 365プラン 2 と SIEM サーバーを統合する|Azure Active Directory () または Microsoft 365 管理センター<https://admin.microsoft.com> (<https://portal.azure.com>) で割り当てられている **グローバル管理者** または **セキュリティ管理者** ロール。 <p> --- **プラス** --- <p> 追加のアプリケーション ([Microsoft Defender セキュリティ センター](/windows/security/threat-protection/microsoft-defender-atp/user-roles)や SIEM サーバーなど) で割り当てられた適切なロール。|

## <a name="next-steps"></a>次の手順

- [脅威トラッカーについて学習する - 新規および注目に値する](threat-trackers.md)
- [配信された悪意のあるメールを検索して調査する (脅威の調査と対応Office 365)](investigate-malicious-email-that-was-delivered.md)
- [脅威の調査と対応Office 365 Microsoft Defender for Endpointと統合する](integrate-office-365-ti-with-mde.md)
- [フィッシング攻撃をシミュレートする](attack-simulation-training.md)
