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
description: Microsoft 365 環境を保護するためのセキュリティ機能を実装するための、Microsoft のサイバーセキュリティ チームからの主な推奨事項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7d376eb7266975dc7582b83bfd4fa5e930ccea4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288171"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の優先事項

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


この記事には、Microsoft 365 環境を保護するためのセキュリティ機能を実装するための、Microsoft のサイバーセキュリティ チームからの主な推奨事項が含まれています。 この記事は、Microsoft Ignite セッションから取り上がっています。Microsoft 365 をサイバーセキュリティ の専門家のように保護します。最初の [30 日間、90](https://www.youtube.com/watch?v=luignzNyR-o)日間、およびそれ以降の最優先事項です。 このセッションは、Mark Simos と、Enterprise Cybersecurity Architects の Matt Kehar が開発および発表しました。

この記事の内容:

- [ロードマップの結果](security-roadmap.md#Roadmap)
- [30 日間 — 強力な迅速な勝ち](security-roadmap.md#Thirdaydays)
- [90 日間 — 強化された保護](security-roadmap.md#Ninetydays)
- [Beyond](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>ロードマップの結果
<a name="Roadmap"> </a>

これらのロードマップの推奨事項は、次の目標を持つ論理的な順序で 3 つのフェーズに分かっています。

****

|時間枠|結果|
|---|---|
|30 日間|迅速な構成: <ul><li>基本的な管理保護。</li><li>ログと分析。</li><li>基本的な ID 保護。</li></ul> <p> テナントの構成。 <p> 関係者を準備します。|
|90 日間|高度な保護: <ul><li>管理者アカウント。</li><li>データとユーザー アカウント。</li></ul> <p> コンプライアンス、脅威、ユーザーのニーズを可視化します。 <p> 既定のポリシーと保護を適応して実装します。|
|Beyond|主要なポリシーとコントロールを調整および調整します。 <p> 保護をオンプレミスの依存関係に拡張します。 <p> ビジネス プロセスやセキュリティ プロセス (法律、内部関係者の脅威など) と統合します。|
|

## <a name="30-days--powerful-quick-wins"></a>30 日間 — 強力な迅速な勝ち
<a name="Thirdaydays"> </a>

タスクはすぐに実行できますので、ユーザーへの影響は少なくて済みます。

****

|分野|タスク|
|---|---|
|セキュリティ管理|<ul><li>セキュア スコアを確認し、現在のスコア ( ) をメモします <https://securescore.office.com> 。</li><li>Office 365 の監査ログを有効にします。 「 [監査ログの検索」を参照してください](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</li><li>[セキュリティ強化のために Microsoft 365 を構成します](tenant-wide-setup-for-increased-security.md)。</li><li>Microsoft 365 セキュリティ センターと Cloud App Security でダッシュボードとレポートを定期的に確認します。</li></ul>|
|脅威に対する保護|[Microsoft 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) を Microsoft Cloud App Security に接続し、異常な動作に関する既定の脅威検出ポリシーを使用して監視を開始します。 異常検出のベースラインを構築するには 7 日かかる。 <p>  管理者アカウントの保護を実装します。<ul><li>管理者アクティビティには専用の管理者アカウントを使用します。</li><li>管理者アカウントに多要素認証 (MFA) を適用します。</li><li>管理者の [アクティビティには、セキュリティが高い Windows 10 デバイス](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) を使います。</li></ul>|
|ID およびアクセス管理|<ul><li>[Azure Active Directory Identity Protection を有効にします](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</li><li>フェデレーション ID 環境では、アカウントのセキュリティ (パスワードの長さ、保存期間、複雑さなど) を適用します。</li></ul>|
|情報保護|情報保護の推奨事項の例を確認します。 情報保護には、組織全体の調整が必要です。 次のリソースの使用を開始する:<ul><li>[GDPR のための Office 365 の情報保護](https://aka.ms/o365gdpr)</li><li>[3 層の保護](../../solutions/configure-teams-three-tiers-protection.md) (共有、分類、データ損失防止、Azure Information Protection を含む) で Teams を構成する</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90 日間 — 強化された保護
<a name="Ninetydays"> </a>

タスクの計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。

****

|分野|Task|
|---|---|
|セキュリティ管理|<ul><li>セキュリティ スコアで、環境に対して推奨されるアクション () を確認します <https://securescore.office.com> 。</li><li>Microsoft 365 セキュリティ センター、Cloud App Security、SIEM ツールでダッシュボードとレポートを定期的に確認し続けます。</li><li>ソフトウェア更新プログラムを探して実装します。</li><li>スピア フィッシング、パスワード スプレー、ブルート フォース パスワード攻撃の攻撃シミュレーションを、攻撃シミュレータ[](attack-simulator.md) [(Office 365 脅威](office-365-ti.md)インテリジェンスに付属) を使用して実行します。</li><li>Cloud App Security の組み込みレポート ([調査] タブ) を確認して、共有リスクを探します。</li><li>コンプライアンス [マネージャーをチェック](../../compliance/compliance-manager.md) して、組織に適用される規制 (GDPR、NIST 800-171 など) の状態を確認します。</li></ul>|
|脅威に対する保護|管理者アカウントの拡張保護を実装します。 <ul><li>管理者 [アクティビティ用に Privileged Access Workstation](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (PAW) を構成します。</li><li>[Azure AD Privileged Identity Management を構成します](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。</li><li>Office 365、Cloud App Security、および AD FS を含むその他のサービスからログ データを収集するセキュリティ情報とイベント管理 (SIEM) ツールを構成します。 監査ログには、90 日間のみデータが格納されます。 SIEM ツールでこのデータをキャプチャすると、データを長い期間保存できます。</li></ul>|
|ID およびアクセス管理|<ul><li>すべてのユーザーに対して MFA を有効にして適用します。</li><li>条件付きアクセスと [関連するポリシーのセットを実装します](microsoft-365-policies-configurations.md)。</li></ul>|
|情報保護| 情報保護ポリシーを適応して実装します。 これらのリソースには、例が含まれます。 <ul><li>[GDPR のための Office 365 の情報保護](https://aka.ms/o365gdpr)</li><li>[3 層の保護を使って Teams を構成する](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Microsoft 365 のデータ損失防止ポリシーと監視ツールは、(Cloud App Security ではなく) Microsoft 365 に保存されているデータに使用します。 <p> 高度なアラート機能 (データ損失防止以外) には、Microsoft 365 で Cloud App Security を使用します。|
|

## <a name="beyond"></a>Beyond
<a name="Beyond"> </a>

これらは、以前の作業を基に構築された重要なセキュリティ対策です。

****

|分野|Task|
|---|---|
|セキュリティ管理|<ul><li>セキュリティ スコア ( ) を使用して、次のアクションの計画を続行します <https://securescore.office.com> 。</li><li>Microsoft 365 セキュリティ センター、Cloud App Security、SIEM ツールでダッシュボードとレポートを定期的に確認し続けます。</li><li>引き続きソフトウェア更新プログラムを探して実装します。</li><li>電子情報開示を法的および脅威の対応プロセスに統合します。</li></ul>|
|脅威に対する保護|<ul><li>オンプレミスの [ID コンポーネント](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (AD、および FS) に対して、セキュリティで保護された特権アクセス (SPA) ADします。</li><li>Cloud App Security を使用して、インサイダーの脅威を監視します。</li><li>Cloud App Security を使用して、シャドウ IT SaaS の使用状況を検出します。</li></ul>|
|ID およびアクセス管理|<ul><li>ポリシーと運用プロセスを調整します。</li><li>Azure AD Identity Protection を使用して、インサイダーの脅威を特定します。</li></ul>|
|情報保護|情報保護ポリシーを調整します。 <ul><li>Microsoft 365 および Office 365 の区別ラベルとデータ損失防止 (DLP)、または Azure Information Protection をサポートしています。</li><li>Cloud App Security のポリシーとアラート。</li></ul>|
|

また、「ペト [キーや WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)などの迅速なサイバー攻撃を軽減する方法」も参照してください。
