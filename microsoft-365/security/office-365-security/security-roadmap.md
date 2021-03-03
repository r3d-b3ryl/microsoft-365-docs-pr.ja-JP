---
title: Microsoft 365 セキュリティ ロードマップ - 最優先事項
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Microsoft 365 環境を保護するためのセキュリティ機能の実装に関する Microsoft のサイバーセキュリティ チームからの推奨事項のトップ。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 728519b4285cf9345052540a0207948f80c18cd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407410"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>セキュリティロードマップ - 最初の 30 日間、90 日間、それ以降の最優先事項

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


この記事では、Microsoft 365 環境を保護するためのセキュリティ機能を実装するための Microsoft のサイバーセキュリティ チームからの推奨事項について説明します。 この記事は、Microsoft Ignite セッション (サイバーセキュリティ の専門家のような Microsoft 365 のセキュリティ保護: 最初の [30 日間、90](https://www.youtube.com/watch?v=luignzNyR-o)日間、およびそれ以降の最優先事項) から適応されています。 このセッションは、Mark Simos と Matt Kemelhar、Enterprise Cybersecurity Architects によって開発され、発表されました。

この記事の内容:

- [ロードマップの結果](security-roadmap.md#Roadmap)
- [30 日間 - 強力なクイック 勝利](security-roadmap.md#Thirdaydays)
- [90 日 — 強化された保護](security-roadmap.md#Ninetydays)
- [Beyond](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>ロードマップの結果
<a name="Roadmap"> </a>

これらのロードマップの推奨事項は、次の目標を持つ論理的な順序で 3 つのフェーズにわたって段階的に行います。

****

|時間枠|結果|
|---|---|
|30 日間|迅速な構成: <ul><li>基本的な管理者保護。</li><li>ログと分析。</li><li>基本的な ID 保護。</li></ul> <p> テナント構成。 <p> 関係者を準備する。|
|90 日間|高度な保護: <ul><li>管理者アカウント。</li><li>データアカウントとユーザー アカウント。</li></ul> <p> コンプライアンス、脅威、ユーザーのニーズを可視化します。 <p> 既定のポリシーと保護を適応して実装します。|
|Beyond|主要なポリシーとコントロールを調整および調整します。 <p> 保護をオンプレミスの依存関係に拡張します。 <p> ビジネスおよびセキュリティ プロセス (法的、内部者の脅威など) と統合します。|
|

## <a name="30-days--powerful-quick-wins"></a>30 日間 - 強力なクイック 勝利
<a name="Thirdaydays"> </a>

タスクはすぐに実行できますので、ユーザーへの影響は少なくて済みます。

****

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>[セキュリティで保護されたスコア] をオンにし、現在のスコア () をメモします <https://securescore.office.com> 。</li><li>365 の監査ログOfficeします。 「 [監査ログの検索」を参照してください](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</li><li>[セキュリティを強化する Microsoft 365 を構成します](tenant-wide-setup-for-increased-security.md)。</li><li>Microsoft 365 セキュリティ センターとクラウド アプリ セキュリティでダッシュボードとレポートを定期的に確認します。</li></ul>|
|脅威に対する保護|[Microsoft 365 を Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) に接続して、異常な動作に対する既定の脅威検出ポリシーを使用して監視を開始します。 異常検出のベースラインを構築するには 7 日かかる。 <p>  管理者アカウントの保護を実装する:<ul><li>管理アクティビティには専用の管理者アカウントを使用します。</li><li>管理者アカウントに多要素認証 (MFA) を適用します。</li><li>管理アクティビティ [には、セキュリティの高い Windows 10 デバイス](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) を使用します。</li></ul>|
|ID およびアクセス管理|<ul><li>[Azure Active Directory IDENTITY Protection を有効にします](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</li><li>フェデレーション ID 環境では、アカウント のセキュリティ (パスワードの長さ、年齢、複雑さなど) を適用します。</li></ul>|
|情報保護|情報保護の推奨事項の例を確認します。 情報保護には、組織全体の調整が必要です。 次のリソースの使用を開始する:<ul><li>[GDPR のための Office 365 の情報保護](https://docs.microsoft.com/compliance/regulatory/gdpr)</li><li>[3 層の保護で](../../solutions/configure-teams-three-tiers-protection.md) Teams を構成する (共有、分類、データ損失防止、Azure 情報保護を含む)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 日 — 強化された保護
<a name="Ninetydays"> </a>

タスクの計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

****

|分野|Task|
|---|---|
|セキュリティ管理|<ul><li>環境 () の推奨アクションについては、「Secure Score」を確認 <https://securescore.office.com> してください。</li><li>Microsoft 365 セキュリティ センター、Cloud App Security、SIEM ツールでダッシュボードとレポートを定期的に確認し続けます。</li><li>ソフトウェア更新プログラムを探して実装します。</li><li>攻撃シミュレーター [(Office 365 Threat Intelligence](office-365-ti.md)に付属) を使用して、[](attack-simulator.md)スピア フィッシング、パスワード スプレー、ブルートフォース パスワード攻撃の攻撃シミュレーションを実行します。</li><li>Cloud App Security の組み込みレポート ([調査] タブ) を確認して、共有リスクを探します。</li><li>コンプライアンス [マネージャーを確認](../../compliance/compliance-manager.md) して、組織に適用される規制 (GDPR、NIST 800-171 など) の状態を確認します。</li></ul>|
|脅威に対する保護|管理者アカウントの拡張保護を実装します。 <ul><li>管理者 [アクティビティ用に特権アクセス ワークステーション](https://docs.microsoft.com/security/compass/privileged-access-devices) (PAW) を構成します。</li><li>[Azure AD特権 ID 管理を構成します](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</li><li>Office 365、Cloud App Security、および AD FS を含む他のサービスからログ データを収集するセキュリティ情報とイベント管理 (SIEM) ツールを構成します。 監査ログには、90 日間だけデータが保存されます。 SIEM ツールでこのデータをキャプチャすると、データを長い期間保存できます。</li></ul>|
|ID およびアクセス管理|<ul><li>すべてのユーザーに対して MFA を有効にして適用します。</li><li>条件付きアクセスと [関連するポリシーのセットを実装します](microsoft-365-policies-configurations.md)。</li></ul>|
|情報保護| 情報保護ポリシーの適応と実装。 これらのリソースには、次の例が含まれます。 <ul><li>[GDPR のための Office 365 の情報保護](https://docs.microsoft.com/compliance/regulatory/gdpr)</li><li>[3 層の保護を使って Teams を構成する](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Microsoft 365 でデータ損失防止ポリシーと監視ツールを使用して、Microsoft 365 に保存されているデータ (クラウド アプリ セキュリティの代わりに) を使用します。 <p> 高度なアラート機能 (データ損失防止以外) には、Microsoft 365 とクラウド アプリ セキュリティを使用します。|
|

## <a name="beyond"></a>Beyond
<a name="Beyond"> </a>

これらは、以前の作業に基く重要なセキュリティ対策です。

****

|分野|Task|
|---|---|
|セキュリティ管理|<ul><li>Secure Score ( ) を使用して、次のアクションの計画を続行 <https://securescore.office.com> します。</li><li>Microsoft 365 セキュリティ センター、Cloud App Security、SIEM ツールでダッシュボードとレポートを定期的に確認し続けます。</li><li>ソフトウェア更新プログラムを引き続き探して実装します。</li><li>電子情報開示を法的および脅威の対応プロセスに統合します。</li></ul>|
|脅威に対する保護|<ul><li>オンプレミス [の ID コンポーネント用のセキュリティ](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) で保護された特権アクセス (SPA) を実装する (AD、AD FS)。</li><li>クラウド アプリ のセキュリティを使用して、内部からの脅威を監視します。</li><li>クラウド アプリ セキュリティを使用してシャドウ IT SaaS の使用状況を確認します。</li></ul>|
|ID およびアクセス管理|<ul><li>ポリシーと運用プロセスを絞り込む。</li><li>Azure AD ID 保護を使用して、内部の脅威を特定します。</li></ul>|
|情報保護|情報保護ポリシーを絞り込む: <ul><li>Microsoft 365 および Office 365 の感度ラベルとデータ損失防止 (DLP)、または Azure Information Protection を使用します。</li><li>Cloud App Security のポリシーとアラート。</li></ul>|
|

「Petya や WannaCrypt などの迅速なサイバー攻撃を軽減する方法 [」も参照してください](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)。
