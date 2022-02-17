---
title: Microsoft Defender for Office 365 - CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.localizationpriority: high
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- intro-overview
description: Microsoft Defender for Office 365 には、安全な添付ファイル、安全なリンク、高度なフィッシング詐欺対策ツール、レポート ツール、および脅威インテリジェンス機能が含まれています。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b6756ba1c0315bb2b89c272d8153715cffe8f976
ms.sourcegitcommit: 19e16b16f144159b55bb4c544403e3642b69e335
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2022
ms.locfileid: "62818566"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) をお持ちのビジネスのお客様を対象としています。Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用していて、Outlook で安全なリンクまたは安全な添付ファイルに関する情報を探している場合は、「[Microsoft 365サブスクライバー向けの高度な Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

Microsoft Defender for Office 365 は、メール メッセージ、リンク (URL)、コラボレーション ツールによってもたらされる悪意のある脅威から組織を保護します。Defender for Office 365 には次のものが含まれます。

- **[脅威保護ポリシー](#configure-microsoft-defender-for-office-365-policies)**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。

- **[レポート](#view-microsoft-defender-for-office-365-reports)**: 組織の Defender for Office 365 パフォーマンスを監視するリアルタイム レポートを表示します。

- **[脅威の調査および反応機能](#use-threat-investigation-and-response-capabilities)**: 最先端のツールを使用して、脅威の調査、把握、シミュレーション、および回避を行います。

- **[自動調査および対応機能](office-365-air.md)**: 脅威の調査および軽減にかかる時間と労力を節約します。

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の対話型のガイド

この対話型のガイドでは、Microsoft Defender for Office 365 を使用して組織を保護する方法について説明します。 Defender for Office 365 が、保護ポリシーの定義、組織への脅威の分析、攻撃への対応にどのように役立つかをご覧いただけます。

[対話型のガイドをチェックしてください](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>はじめに

Microsoft Defender for Office 365 を初めて使用している場合、または *実行しながら* 最適な方法を学ぶ場合は、この記事を参照しながら、初期 Defender for Office 365 構成をチャンクに分割し、調査し、レポートを表示することをお勧めします。 論理的な初期構成チャンクは次の通りです。

- 名前に "*対策*" を使用してすべてを構成します。
  - マルウェア対策
  - フィッシング詐欺対策
  - スパム対策
- 名前に "*安全*" を使用してすべてを設定します。
  - 安全なリンク
  - 安全な添付ファイル
- ワークロードを保護する (例: OSharePoint Online、OneDrive と Teams)
- ゼロアワー自動消去 (ZAP) を使用して保護します。

詳細については、 [このリンクをクリック](protect-against-threats.md)してください。

> [!NOTE]
> Microsoft Defender for Office 365 には、2 種類のプランがあります。 "リアルタイム検出" を使用している場合は **プラン 1** で、脅威エクスプローラーを使用している場合は **プラン 2** が表示されます。 このプランは、表示されるツールに影響しますので、お客様のプランについて理解していることをご確認ください。

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 プラン 1 およびプラン 2

次の表は、各プランに含まれる機能をまとめたものです。

****

|Microsoft Defender for Office 365 プラン 1|Defender for Office 365 プラン 2|
|---|---|
|構成、保護、および検出機能: <ul><li>[添付ファイル保護](safe-attachments.md)</li><li>[リンク保護](safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の安全な添付ファイル](mdo-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[リアルタイム検出](threat-explorer.md)</li></ul>|Defender for Office 365 プラン 1 の機能 <p> --- プラスのもの --- <p> 自動化、調査、修復、教育の機能: <ul><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](office-365-air.md)</li><li>[攻撃シミュレーション トレーニング](attack-simulation-training.md)</li><li>[Microsoft 365 Defender の高度な追求](advanced-hunting-overview.md)</li><li>[Microsoft 365 Defender のインシデント](investigate-incidents.md)</li><li>[Microsoft 365 Defender のアラート](investigate-alerts.md)</li></ul>|


- Microsoft Defender for Office 365 プラン 2 は、Office 365 E5、Office 365 A5、Microsoft 365 E5 に含まれています。

- Microsoft Defender for Office 365 プラン 1 は、Microsoft 365 Business Premium に含まれています。

- Microsoft Defender for Office 365 プラン 1 および Microsoft Defender for Office 365 プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして提供されています。 詳細については、「[Microsoft Defender for Office 365 プラン全体での機能の可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

- [安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Microsoft Defender for Office 365 プランには含まれません) を持つユーザーのみが利用できます。

- 現在のサブスクリプションに Microsoft Defender for Office 365 が含まれていない場合に購入を希望する場合は、[営業担当者に問い合わせて試用版の使用を開始](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)し、お客様の組織にとって Microsoft Defender for Office 365 がどのようなメリットになるかを確認してください。

- Microsoft Defender for Office 365 P2 をご利用のお客様は、**Microsoft 365 Defender 統合** にアクセスすると、インシデントやアラートを効率的に検出して確認しながら対応することができます。

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Microsoft Defender for Office 365 のポリシーを構成する

Microsoft Defender for Office 365 を使用すると、組織のセキュリティ チームは、Microsoft 365 Defender ポータルの <https://security.microsoft.com> で、**[メール & コラボレーション]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** でポリシーを定義することで、保護を構成できます。 または、 <https://security.microsoft.com/threatpolicy> を使用して、**"脅威ポリシー"** ページに直接移動することもできます。

[このビデオ](https://www.youtube.com/watch?v=vivvTmWJ_3c)を見て詳細をご確認ください。

> [!TIP]
> 定義するポリシーの簡便なリストについては、「[脅威から保護する](protect-against-threats.md)」を参照してください。

## <a name="defender-for-office-365-policies"></a>Defender for Office 365 ポリシー

組織で定義されているポリシーにより、定義済み脅威に対する動作と保護レベルが決まります。 ポリシー オプションは、非常に柔軟です。 たとえば、組織のセキュリティ チームは、ユーザー、組織、受信者、ドメイン レベルで詳細に脅威保護を設定できます。 新しい脅威や課題が毎日出現するため、ポリシーを定期的に確認することが重要です。

- **[安全な添付ファイル機能](safe-attachments.md)**: 悪意のあるコンテンツがないかどうかメールの添付ファイルを確認して、メッセージング システムを保護できるゼロデイ保護機能を提供します。 ウイルス/マルウェアの署名を持たないすべてのメッセージと添付ファイルを特別な環境にルートし、機械学習と分析技術を使用して悪意を検出します。 疑わしいアクティビティが見つからない場合、メッセージはメールボックスに転送されます。 詳細については、「[安全な添付ファイル ポリシーを設定する](set-up-safe-attachments-policies.md)」を参照してください。

- **[安全なリンク](safe-links.md)**: メール メッセージや Office ファイルなどで、URL をクリックした時に検証を行います。 保護は継続的に行われ、メッセージおよび Office 環境全体に適用されます。 クリックごとにリンクがスキャンされます。安全なリンクは常にアクセスでき、悪意のあるリンクは動的にブロックされます。 詳細については、「[安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」をご覧ください。

- **[SharePoint、OneDrive、Microsoft Teams 用の 安全な添付ファイル](mdo-for-spo-odb-and-teams.md)**: チーム サイトやドキュメント ライブラリ内で悪意のあるファイルを特定してブロックすることで、ユーザーが共同作業でファイルを共有する際に組織を保護します。 詳細については、「[SharePoint、OneDrive、Microsoft の Defender for Office 365 を有効にする](turn-on-mdo-for-spo-odb-and-teams.md)」を参照してください。

- **[Defender for Office 365 のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: ユーザー、内部およびカスタム ドメインの偽装を検出します。 この機能は、コンピューターの学習モデルや高度な偽装検出アルゴリズムを適用してフィッシング攻撃に回避します。 詳細については、「[Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する](configure-mdo-anti-phishing-policies.md)」を参照してください。

## <a name="view-microsoft-defender-for-office-365-reports"></a>Microsoft Defender for Office 365 レポートを表示する

Microsoft Defender for Office 365 には、Defender for Office 365 を監視するための[レポート](view-reports-for-mdo.md)が含まれています。 Microsoft 365 Defender ポータルの <https://security.microsoft.com> で、**レポート** \> **[メールとコラボレーション]** \> **[メールとコラボレーション レポート]** でレポートに直接アクセスできます。 または、<https://security.microsoft.com/securityreports> を使用して、"**メールとコラボレーション レポート"** ページに直接移動することもできます。

レポートはリアルタイムで更新され、最新の分析情報を提供します。 また、これらのレポートは推奨事項を提供し、間近に迫った脅威を警告します。 定義済みレポートには次のものが含まれます:

- [脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)
- [脅威保護の状態レポート](view-reports-for-mdo.md#threat-protection-status-report)
- レポートは、上記のもの以外にもいくつかあります。

## <a name="use-threat-investigation-and-response-capabilities"></a>脅威の調査および対応機能を使用する

Microsoft Defender for Office 365 プラン 2 には、組織のセキュリティ チームが悪意のある攻撃を予測、把握、および回避するために、クラス最高の[脅威の調査および対応のツール](office-365-ti.md)が含まれます。

- **[脅威トラッカー](threat-trackers.md)** は、一般的なサイバーセキュリティの問題に関する最新のインテリジェンスを提供します。 たとえば、最新のマルウェアに関する情報を表示し、組織に対する実際の脅威になる前に対策を講じることができます。 使用可能な脅威トラッカーには、[[注目のトラッカー](threat-trackers.md#noteworthy-trackers)]、[[急上昇中のトラッカー](threat-trackers.md#trending-trackers)]、[[追跡されたクエリ](threat-trackers.md#tracked-queries)]、[[保存されたクエリ](threat-trackers.md#saved-queries)] があります。

- **[Threat Explorer (またはリアルタイム検出)](threat-explorer.md)** (エクスプローラーとも呼ばれます) は、最近の脅威を特定して分析できるリアルタイム レポートです。カスタム期間のデータを表示するようにエクスプローラーを構成できます。

- **[攻撃シミュレーションのトレーニング](attack-simulation-training.md)** を使用すると、現実的な攻撃シナリオを組織で実行して、脆弱性を特定することができます。 スピア フィッシング資格情報獲得と添付ファイルの攻撃、パスワード スプレーとブルート フォース パスワード攻撃など、現在の種類の攻撃のシミュレーションを利用できます。

## <a name="save-time-with-automated-investigation-and-response"></a>自動化された調査と対応で時間を節約する

(**新機能!**) 潜在的なサイバー攻撃を調査している場合は、期限厳守です。 脅威をより早く特定して軽減できれば、組織はより良くなります。 [自動調査および対応](office-365-air.md) (AIR) 機能には、アラートがトリガーされたときなどには自動的に、またはエクスプローラーのビューから手動で起動できるセキュリティ プレイブックのセットが含まれています。 AIR は、セキュリティ運用チームの脅威を軽減するための時間と労力を効果的かつ効率的に節約できます。 詳細については、「[Office 365 での AIR](office-365-air.md)」を参照してください。

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Microsoft Defender for Office 365 の機能を使用するために必要な権限

Microsoft Defender for Office 365 の機能にアクセスするには、適切な役割が割り当てられている必要があります。次のテーブルに例がいくつか示されています。

<br>

****

|役割または役割グループ|追加情報|
|---|---|
|グローバル管理者 (組織管理)|このロールは、Azure Active Directory または Microsoft 365 Defender ポータルで割り当てることができます。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。|
|セキュリティ管理者|このロールは、Azure Active Directory または Microsoft 365 Defender ポータルで割り当てることができます。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。|
|Exchange Online の組織の管理|[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online の PowerShell](/powershell/exchange/exchange-online-powershell)|
|検索と消去|このロールは、Microsoft 365 Defender ポータルまたはMicrosoft 365 コンプライアンス センターでのみ使用できます。 詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」および「[Microsoft 365 コンプライアンス センターのアクセス許可](../../compliance/microsoft-365-compliance-center-permissions.md)」を参照してください。|
|||

## <a name="get-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 を取得する

Microsoft Defender for Office 365 は、Microsoft 365 E5、Office 365 E5、Office 365 A5、Microsoft 365 Business Premium などの特定のサブスクリプションに含まれています。 サブスクリプションに Defender for Office 365 が含まれていない場合は、特定のサブスクリプションへのアドオンとして Defender for Office 365 プラン 1 または Defender for Office 365 プラン 2 を購入できます。 詳細については、次のリソースを参照してください。

- Defender for Office 365 プランを含むサブスクリプションのリストについては、「[Microsoft Defender for Office 365 の可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)」を参照してください。

- プラン 1 と 2 に含まれる機能のリストについては、「[Microsoft Defender for Office 365 プランで利用できる機能](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」

- [適切な Microsoft Defender for Office 365 を入手](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)して、プランを比較し、Defender for Office 365 を購入してください。

- [無料試用版を開始する](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の新機能

Microsoft Defender for Office 365 には継続的に新機能が追加されています。 詳細については、次のリソースを参照してください。

- 「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365)」は、開発およびロール アウトの新機能の一覧を提供します。

- [Microsoft Defender for Office 365 サービスの説明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)は、Defender for Office 365 プラン全体の機能と可用性について説明しています。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
- [Microsoft 365 Defender での自動調査および対応 (AIR)](../defender/m365d-autoir.md)
