---
title: Microsoft 365 セキュリティロードマップ-最優先事項
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Microsoft の cybersecurity チームからの、Microsoft 365 環境を保護するためのセキュリティ機能の実装に関する主な推奨事項。 '
ms.openlocfilehash: 452ce2a303f02cadfcdcbe12310f2538d33a24e7
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615806"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>セキュリティロードマップ-最初の30日間、90日以降の優先度

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


この記事には、microsoft の cybersecurity チームからの Microsoft 365 環境を保護するためのセキュリティ機能の実装に関する主な推奨事項が含まれています。 この記事は、Microsoft Ignite session ( [cybersecurity pro のようなセキュリティで保護された microsoft 365 のように、最初の30日間、90日以降) に適用](https://www.youtube.com/watch?v=luignzNyR-o)されます。 このセッションは、Mark Simos および Kemelhar, エンタープライズ Cybersecurity アーキテクトによって開発および提供されました。

この記事の内容:

- [ロードマップの結果](security-roadmap.md#Roadmap)
- [30日-強力な高速 wins](security-roadmap.md#Thirdaydays)
- [90日—保護の強化](security-roadmap.md#Ninetydays)
- [超え](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>ロードマップの結果
<a name="Roadmap"> </a>

これらのロードマップの推奨事項は、次の目標を使用して、3つのフェーズに論理的な順序で段階的に展開されています。

****

|時間枠|結果|
|---|---|
|30 日間|高速構成: <ul><li>基本的な管理者による保護。</li><li>ログと分析。</li><li>基本的な id 保護。</li></ul> <p> テナントの構成。 <p> 関係者を準備します。|
|90 日間|高度な保護: <ul><li>管理者アカウント</li><li>データおよびユーザーアカウント。</li></ul> <p> コンプライアンス、脅威、およびユーザーのニーズを把握できます。 <p> 既定のポリシーと保護を調整して実装します。|
|超え|主要なポリシーと制御を調整し、調整します。 <p> オンプレミスの依存関係への保護を拡張します。 <p> ビジネスおよびセキュリティプロセス (法務、insider の脅威など) と統合します。|
|

## <a name="30-days--powerful-quick-wins"></a>30日-強力な高速 wins
<a name="Thirdaydays"> </a>

タスクはすぐに実行できますので、ユーザーへの影響は少なくて済みます。

****

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>[セキュリティで保護されたスコア] を確認し、現在のスコアをメモし <https://securescore.office.com> ます ()。</li><li>Office 365 の監査ログを有効にします。 「 [監査ログを検索する](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。</li><li>[セキュリティを強化するために、Microsoft 365 を構成](tenant-wide-setup-for-increased-security.md)します。</li><li>Microsoft 365 セキュリティセンターおよび Cloud App Security のダッシュボードとレポートを定期的にレビューします。</li></ul>|
|脅威保護|[Microsoft 365 を Microsoft Cloud App Security に接続](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) して、異常な動作に関する既定の脅威検出ポリシーを使用した監視を開始します。 異常検出のベースラインを構築するには、7日間かかります。 <p>  管理者アカウントの保護を実装します。<ul><li>管理者アクティビティに専用の管理者アカウントを使用します。</li><li>管理者アカウントに対して多要素認証 (MFA) を強制します。</li><li>管理者アクティビティには、 [高度にセキュリティで保護された Windows 10 デバイス](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) を使用します。</li></ul>|
|ID およびアクセス管理|<ul><li>[Azure Active Directory Id 保護を有効に](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)します。</li><li>フェデレーション id 環境では、アカウントセキュリティ (パスワードの長さ、年齢、複雑さなど) を適用します。</li></ul>|
|情報保護|情報保護に関する推奨事項の例を確認します。 情報保護には、組織全体にわたる調整が必要です。 次のリソースの使用を開始する:<ul><li>[GDPR のための Office 365 の情報保護](https://aka.ms/o365gdpr)</li><li>[3 層の保護](../../solutions/configure-teams-three-tiers-protection.md) (共有、分類、データ損失防止、および Azure Information protection を含む) を使用して Teams を構成する</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90日—保護の強化
<a name="Ninetydays"> </a>

タスクの計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

****

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>お使いの環境で推奨されるアクションについては、「Secure Score」を確認 <https://securescore.office.com> してください ()。</li><li>引き続き、Microsoft 365 セキュリティセンター、Cloud App Security、および SIEM ツールのダッシュボードとレポートを定期的に確認してください。</li><li>ソフトウェア更新プログラムを検索して実装します。</li><li>[アタックシミュレータ](attack-simulator.md)を使用して、スピアーフィッシング、パスワードスプレー、ブルートフォースパスワード攻撃に対する攻撃のシミュレーションを行います ( [Office 365 の脅威インテリジェンス](office-365-ti.md)に含まれています)。</li><li>Cloud App Security ([調査] タブ) の組み込みレポートを確認して、共有のリスクを探します。</li><li>組織に適用される規制の状態を確認するために [コンプライアンスマネージャー](https://docs.microsoft.com/microsoft-365/compliance/compliance-manager) をチェックします (GDPR、NIST 800-171 など)。</li></ul>|
|脅威保護|管理者アカウントの強化された保護を実装します。 <ul><li>管理者アクティビティ用に [特権アクセスワークステーション](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAWs) を構成します。</li><li>[AZURE AD の特権 Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)を構成します。</li><li>セキュリティ情報およびイベント管理 (SIEM) ツールを構成して、Office 365、Cloud App Security、およびその他のサービス (AD FS を含む) からログデータを収集します。 監査ログには、90日のみのデータが格納されます。 このデータを SIEM ツールで取得すると、長期間にデータを格納することができます。</li></ul>|
|ID およびアクセス管理|<ul><li>すべてのユーザーに対して MFA を有効にし、適用します。</li><li>一連の [条件付きアクセスと関連ポリシー](microsoft-365-policies-configurations.md)を実装します。</li></ul>|
|情報保護| 情報保護ポリシーを調整して実装します。 これらのリソースには例があります。 <ul><li>[GDPR のための Office 365 の情報保護](https://aka.ms/o365gdpr)</li><li>[3 層の保護を使ってチームを構成する](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Microsoft 365 のデータ損失防止ポリシーおよび監視ツールを使用して、Microsoft 365 に保存されたデータ (Cloud App Security ではない) を使用します。 <p> 高度な警告機能 (データ損失防止) については、Microsoft 365 で Cloud App Security を使用します。|
|

## <a name="beyond"></a>超え
<a name="Beyond"> </a>

これらは、前の作業で構築された重要なセキュリティ対策です。

****

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>セキュリティで保護されたスコアを使用して、次のアクションの計画を続行 <https://securescore.office.com> します ()。</li><li>引き続き、Microsoft 365 セキュリティセンター、Cloud App Security、および SIEM ツールのダッシュボードとレポートを定期的に確認してください。</li><li>引き続きソフトウェア更新プログラムを検索して実装します。</li><li>電子情報開示を法的および脅威対応プロセスに統合する。</li></ul>|
|脅威保護|<ul><li>オンプレミスの id コンポーネント (AD、AD FS) に [安全な特権アクセス](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) を実装します。</li><li>内部者の脅威を監視するには、Cloud App Security を使用します。</li><li>Cloud App Security を使用して、シャドウ IT SaaS の使用状況を検出します。</li></ul>|
|ID およびアクセス管理|<ul><li>ポリシーおよび運用プロセスを調整します。</li><li>Azure AD Identity Protection を使用して、内部の脅威を特定します。</li></ul>|
|情報保護|情報保護ポリシーを調整する: <ul><li>Microsoft 365 および Office 365 の機密ラベルとデータ損失防止 (DLP)、または Azure Information Protection。</li><li>Cloud App Security ポリシーとアラート。</li></ul>|
|

また、「 [Petya および WannaCrypt などのラピッド cyberattacks を緩和する方法](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)」も参照してください。
