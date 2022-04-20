---
title: Microsoft 365セキュリティ ロードマップ - 最優先事項
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 08/20/2021
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Microsoft 365環境を保護するためのセキュリティ機能を実装するための Microsoft のサイバーセキュリティ チームからの最高の推奨事項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b39edc8adbe16d7f085ca9fec9f30d45f484838
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64974259"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

この記事には、Microsoft 365環境を保護するためのセキュリティ機能を実装するための Microsoft のサイバーセキュリティ チームからの最高の推奨事項が含まれています。 この記事は、Microsoft Ignite セッション ([サイバーセキュリティ担当者のようなセキュリティで保護されたMicrosoft 365: 最初の 30 日間、90 日間、およびそれ以降の最優先事項](https://www.youtube.com/watch?v=luignzNyR-o)) から調整されています。 このセッションは、Mark Simos と Matt Kemelhar (Enterprise Cybersecurity Architects) によって開発され、発表されました。

この記事の内容:

- [ロードマップの成果](security-roadmap.md#Roadmap)
- [30 日間 — 強力なクイック 勝利](security-roadmap.md#Thirdaydays)
- [90 日間 — 強化された保護](security-roadmap.md#Ninetydays)
- [を超えて](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>ロードマップの成果
<a name="Roadmap"> </a>

これらのロードマップの推奨事項は、次の目標を持つ論理的な順序で 3 つのフェーズにわたってステージングされます。

|時間枠|結果|
|---|---|
|30 日間|迅速な構成: <ul><li>基本的な管理者保護。</li><li>ログ記録と分析。</li><li>基本的な ID 保護。</li></ul> <p> テナントの構成。 <p> 関係者を準備する。|
|90 日間|高度な保護: <ul><li>管理者アカウント。</li><li>データとユーザー アカウント。</li></ul> <p> コンプライアンス、脅威、ユーザーのニーズを可視化します。 <p> 既定のポリシーと保護を調整して実装します。|
|を超えて|キー ポリシーとコントロールを調整および調整します。 <p> 保護をオンプレミスの依存関係に拡張します。 <p> ビジネスおよびセキュリティ プロセス (法的、インサイダーの脅威など) と統合します。|

## <a name="30-days--powerful-quick-wins"></a>30 日間 — 強力なクイック 勝利
<a name="Thirdaydays"> </a>

タスクはすぐに実行できますので、ユーザーへの影響は少なくて済みます。

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>セキュア スコアを確認し、現在のスコア (<https://security.microsoft.com/securescore>) をメモします。</li><li>Office 365の監査ログを有効にします。 [「監査ログを検索する」を参照してください](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</li><li>[セキュリティを強化するためにMicrosoft 365を構成します](tenant-wide-setup-for-increased-security.md)。</li><li>Microsoft 365 Defender ポータルとDefender for Cloud アプリでダッシュボードとレポートを定期的に確認します。</li></ul>|
|脅威に対する保護|[異常な動作に](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)既定の脅威検出ポリシーを使用して監視を開始するMicrosoft Defender for Cloud AppsをConnect Microsoft 365します。 異常検出のベースラインを構築するには、7 日間かかります。 <p>  管理者アカウントの保護を実装する:<ul><li>管理者アクティビティには専用の管理者アカウントを使用します。</li><li>管理者アカウントに多要素認証 (MFA) を適用します。</li><li>管理者アクティビティ[には、セキュリティの高いWindows デバイス](/windows-hardware/design/device-experiences/oem-highly-secure)を使用します。</li></ul>|
|ID およびアクセス管理|<ul><li>[Azure Active Directory Identity Protection を有効にします](/azure/active-directory/active-directory-identityprotection-enable)。</li><li>フェデレーション ID 環境の場合は、アカウントのセキュリティ (パスワードの長さ、年齢、複雑さなど) を適用します。</li></ul>|
|情報保護|情報保護に関する推奨事項の例を確認します。 情報保護には、組織全体の調整が必要です。 次のリソースの使用を開始する:<ul><li>[GDPR のための Office 365 の情報保護](/compliance/regulatory/gdpr)</li><li>[3 層の保護](../../solutions/configure-teams-three-tiers-protection.md) (共有、分類、Microsoft Purview データ損失防止、Azure Information Protectionを含む) でTeamsを構成する</li></ul>|

## <a name="90-days--enhanced-protections"></a>90 日間 — 強化された保護
<a name="Ninetydays"> </a>

タスクの計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>お使いの環境に推奨されるアクションについては、セキュア スコアを確認してください (<https://security.microsoft.com/securescore>)。</li><li>Microsoft 365 Defender ポータル、Defender for Cloud アプリ、SIEM ツールでダッシュボードとレポートを定期的に確認し続けます。</li><li>ソフトウェア更新プログラムを探して実装します。</li><li>攻撃シミュレーション トレーニング ([Office 365脅威インテリジェンス](office-365-ti.md)に付属) を使用して、スピア フィッシング、パスワード スプレー、ブルートフォース パスワード攻撃の[攻撃シミュレーション](attack-simulation-training.md)を実行します。</li><li>Defender for Cloud Apps の組み込みレポート ([調査] タブ) を確認して、リスクの共有を探します。</li><li>[コンプライアンス マネージャー](../../compliance/compliance-manager.md)を確認して、組織に適用される規制 (GDPR、NIST 800-171 など) の状態を確認します。</li></ul>|
|脅威に対する保護|管理者アカウントの強化された保護を実装します。 <ul><li>管理者アクティビティ [用に Privileged Access Workstations](/security/compass/privileged-access-devices) (PAW) を構成します。</li><li>Azure AD Privileged Identity Managementを構成[します](/azure/active-directory/active-directory-privileged-identity-management-configure)。</li><li>Office 365、Defender for Cloud Apps、および AD FS を含むその他のサービスからログ データを収集するためのセキュリティ情報とイベント管理 (SIEM) ツールを構成します。 監査ログには、90 日間だけデータが格納されます。 SIEM ツールでこのデータをキャプチャすると、より長い期間データを格納できます。</li></ul>|
|ID およびアクセス管理|<ul><li>すべてのユーザーに対して MFA を有効にして適用します。</li><li>[条件付きアクセスと関連するポリシー](microsoft-365-policies-configurations.md)のセットを実装します。</li></ul>|
|情報保護| 情報保護ポリシーを調整して実装する。 これらのリソースには、次の例があります。 <ul><li>[GDPR のための Office 365 の情報保護](/compliance/regulatory/gdpr)</li><li>[3 層の保護を使って Teams を構成する](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Microsoft 365に格納されたデータ (Defender for Cloud アプリの代わりに) に Microsoft Purview でデータ損失防止ポリシーと監視ツールを使用します。 <p> 高度なアラート機能 (データ損失防止以外) には、Defender for Cloud アプリとMicrosoft 365を使用します。|

## <a name="beyond"></a>を超えて
<a name="Beyond"> </a>

これらは、前の作業に基づいて構築された重要なセキュリティ対策です。

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>セキュア スコア (<https://security.microsoft.com/securescore>) を使用して、次のアクションの計画を続行します。</li><li>Microsoft 365 Defender ポータル、Defender for Cloud アプリ、SIEM ツールでダッシュボードとレポートを定期的に確認し続けます。</li><li>ソフトウェア更新プログラムを引き続き検索して実装します。</li><li>電子情報開示を法的および脅威対応プロセスに統合します。</li></ul>|
|脅威に対する保護|<ul><li>オンプレミスの ID コンポーネント (AD、AD FS) に [セキュリティで保護された特権アクセス](/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) を実装します。</li><li>Defender for Cloud アプリを使用して、インサイダーの脅威を監視します。</li><li>Defender for Cloud アプリを使用してシャドウ IT SaaS の使用状況を検出します。</li></ul>|
|ID およびアクセス管理|<ul><li>ポリシーと運用プロセスを絞り込みます。</li><li>Azure AD Identity Protection を使用してインサイダーの脅威を特定します。</li></ul>|
|情報保護|情報保護ポリシーを絞り込む: <ul><li>機密ラベルとデータ損失防止 (DLP)、または Azure Information ProtectionをMicrosoft 365してOffice 365します。</li><li>Defender for Cloud アプリのポリシーとアラート。</li></ul>|

「 [Petya や WannaCrypt などの迅速なサイバー攻撃を軽減する方法](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)」も参照してください。
