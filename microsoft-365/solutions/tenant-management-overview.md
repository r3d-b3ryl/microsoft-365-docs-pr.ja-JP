---
title: エンタープライズ向け Microsoft 365 のテナント管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントの計画、展開、および継続的な運用の概要。
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405680"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>エンタープライズ向け Microsoft 365 のテナント管理

クラウド コンピューティングを使用して組織のデジタル変換へのパスを作成するには、作業員が生産性、コラボレーション、パフォーマンス、プライバシー、コンプライアンス、セキュリティに頼れる基盤が必要です。

Microsoft 365 テナントの正しい構成により、その基盤が提供され、従業員は作業の完了に集中し、IT 部門は追加のビジネス価値を提供するエンドツーエンドのソリューションに集中できます。 

このソリューションでは、次の手順で、その基盤の構成を説明します。

1. テナントを決定する
2. ネットワークを最適化する
3. ID を同期し、セキュリティで保護されたサインインを適用する
4. Windows デバイス、Office、オンプレミスのサーバーとデータOffice移行する
5. デバイスとアプリの管理を展開する

しかし、最初に、テナントとは何か、また、堅固な基盤を提供するテナントの外観を理解するために少し時間を取って説明します。

## <a name="a-microsoft-365-tenant-defined"></a>定義された Microsoft 365 テナント

Microsoft 365 テナントは、Microsoft 365 のサービスと、ヨーロッパや北アメリカなどの特定の既定の場所に格納されている組織データの専用インスタンスです。 この場所は、組織のテナントを作成するときに指定されます。 各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。 Microsoft 365 E3 や E5 など、Microsoft から 1 つ以上の製品を購入する場合は、Microsoft 365 テナントを作成し、それぞれのライセンスのセットを作成します。

Microsoft 365 テナントには Azure Active Directory (Azure AD) テナントも含まれています。これは、ユーザー アカウント、グループ、その他のオブジェクト用の Azure AD の専用インスタンスです。 各 Azure ADテナントは、個別で一意であり、他のすべての Azure テナントとADされます。 組織では、Azure サブスクリプションでセットアップできる複数の Azure AD テナントを使用できますが、Microsoft 365 テナントは、テナントの作成時に作成された Azure AD テナントを 1 つのみ使用できます。 

次に例を示します：

![Azure サービス テナントを持つ Microsoft 365 テナントAD例](../media/tenant-management-overview/tenant-management-example-tenant.png)

*テナント管理* は、Microsoft 365 テナントの計画、展開、および継続的な操作です。 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>十分に設計され、運用されているテナントの属性

テナントの正しい名前と場所を超えて、Microsoft Teams や Exchange Online などのクラウド生産性アプリに関するユーザー エクスペリエンスが効果的で安全で、パフォーマンスを高めるには、計画、展開、管理のための追加の要素があります。 &mdash; &mdash;

要素は次のとおりです。

- 製品 (サブスクリプション) とライセンスの正しいセットがあります。
  - 一連の製品は、ビジネス、IT、およびセキュリティのニーズに一致します。
  - 従業員に対して適切な数のライセンスと、スタッフの予想される変更点があります。
- ネットワークの場合:
  - 正しい名前をDNS ドメインしました。
  - エンタープライズ ネットワークの場合、オンサイト ワーカー向けに Microsoft ネットワークへのネットワーク トラフィックを最適化しました。
  - VPN クライアントを使用しているリモート ワーカーのネットワーク トラフィックを最適化しました。
- Active Directory ドメイン サービス (DS) アカウント、AD、その他のオブジェクトを同期しました。
  - Azure ADテナント アカウントは、電子メール アドレスの正しい DNS ドメインを使用して Exchange Online メールボックスにマップされます。
  - ユーザー アカウントには、正しい購入済み製品 (Microsoft 365 E3 や E5 など) から適切なライセンスが割り当てされています。
- 強力な ID とアクセス管理を構成しました。
  - パスワードレス認証または多要素認証 (MFA) によるセキュリティで保護されたユーザー サインインが必要です。
  - より高いレベルのセキュリティのためにサインイン要件と制限を適用する条件付きアクセス ポリシーがあります。
- オンプレミスのサーバー Officeデータはクラウド アプリに移行しているか、ハイブリッド構成で使用されています。
- Intune または Microsoft 365 に組み込んだ Basic Mobility and Security を使用してデバイス管理を行っています。
  - 組織が所有するデバイスが登録され、管理されます。
  - 個人用デバイス用のアプリは管理されます。

これらすべての要素が配置された Microsoft 365 テナントの例を次に示します。

![Microsoft 365 テナントの例](../media/tenant-management-overview/tenant-management-tenant-config.png)

この図では、Microsoft 365 テナントには次の情報が含まれています。

- Microsoft 365 E3 および E5 の製品とライセンス。
- Microsoft 365 生産性アプリ。
- Intune には、登録済みデバイスとデバイスポリシーとアプリケーション ポリシーがあります。
- ユーザー アカウントAD (グループなどのディレクトリ オブジェクトは表示されません)、ドメイン、条件付きアクセス ポリシーが同期されている Azure テナント。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>エンタープライズ向け Microsoft 365 のテナント機能

次のセクションと表は、このソリューションの手順の主な機能とライセンスの一覧です。

### <a name="tenant"></a>テナント

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| 複数のテナント | 各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。 複数のテナントがある場合、それらを管理し、ユーザーにサービスを提供する際には、制限と追加の考慮事項があります。 | Microsoft 365 E3 または E5 | 
| テナント間でのメールボックスの移行 | テナント管理者は、オンプレミス システムで最小限のインフラストラクチャ依存関係を持つテナント間でメールボックスを移動できます。 これにより、オフボードメールボックスとオンボードメールボックスが不要になります。 | Microsoft 365 E3 または E5 | 
| Multi-Geo | テナントは、データ常駐の要件を満たすために選択した他のデータセンターの地理的な場所にデータを保存できます。 | Microsoft 365 E3 または E5 | 
| コア データを新しいデータセンター geo に移動する | Microsoft が追加の容量とコンピューティング リソース用に新しいデータセンター geo を追加すると、主要な顧客データに対する地域内データ常駐のデータセンター geo の移動を要求できます。 | Microsoft 365 E3 または E5 | 
||||

### <a name="networking"></a>ネットワーク

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| ネットワークインサイト | Microsoft 365 テナントから収集されたネットワーク パフォーマンス指標は、オフィスの場所のネットワーク境界を設計するのに役立ちます。 | Microsoft 365 E3 または E5 | 
| エンドポイントの更新を自動化する | クライアント PAC ファイルとネットワーク デバイスとサービス内の Microsoft 365 エンドポイントの構成と継続的な更新を自動化します。 | Microsoft 365 E3 または E5 | 
||||

### <a name="identity"></a>ID

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure ドメイン テナントADする    | ユーザー アカウント、グループ、その他のオブジェクトのオンプレミス ID プロバイダーを活用します。 | Microsoft 365 E3 または E5 |
| セキュリティの既定値が適用されている MFA   | サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。   | Microsoft 365 E3 または E5 |
| 条件付きアクセスが適用されている MFA| 条件付きアクセス ポリシーを使用してサインインの属性に基づいて MFA を要求します。    | Microsoft 365 E3 または E5 | 
| リスクベースの条件付きアクセスが適用されている MFA   | ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。 | Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3 | 
| セルフサービスによるパスワードのリセット (SSPR)    | ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。  | Microsoft 365 E3 または E5 |
||||

### <a name="migration"></a>移行

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| Windows 10 に移行する | Windows 7 または Windows 8.1 を実行するデバイスを Windows 10 Enterprise に移行します。 | Microsoft 365 E3 または E5 に含まれる Windows 10 Enterprise ライセンス | 
| エンタープライズ向け Microsoft 365 Apps への移行 | Word や powerPoint Officeクライアント アプリを、新しい機能で更新されたクラウドからインストールされたバージョンに移行します。 | Microsoft 365 E3 または E5 | 
| オンプレミスのサーバーとデータを Microsoft 365 に移行する | Exchange メールボックス、SharePoint サイト、Skype for Business Online を Microsoft 365 クラウド サービスに移行します。 | Microsoft 365 E3 または E5 | 
||||

### <a name="device-and-app-management"></a>デバイスおよびアプリの管理

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| Microsoft Intune | モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を提供するクラウドベースのサービスで、携帯電話、タブレット、ラップトップなど、組織のアプリケーションとデバイスの使用方法を制御します。 | Microsoft 365 E3 または E5 | 
| 基本的なモビリティとセキュリティ | この組み込みサービスを使用して、iPhone、iPad、Android、Windows 電話など、ユーザーのモバイル デバイスをセキュリティで保護して管理します。  | Microsoft 365 E3 または E5 | 
||||

## <a name="next-steps"></a>次の手順

Microsoft 365 テナントを設定および管理するには、次の手順を実行します。

1. [テナントを決定する](tenant-management-tenants.md)
2. [ネットワークを最適化する](tenant-management-networking.md)
3. [ID を同期し、セキュリティで保護されたサインインを適用する](tenant-management-identity.md)
4. [オンプレミスのサーバーとデータOffice移行する](tenant-management-migration.md)
5. [デバイスとアプリの管理を展開する](tenant-management-device-management.md)

[![Microsoft 365 テナントを展開および管理する手順](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

各手順では、展開オプション、結果、および継続的なメンテナンス タスクについて説明します。

架空の代表的な多国籍組織が Microsoft 365 テナントの要素を展開した方法を理解するには、「Contoso のケース スタディ」 [を参照してください](../enterprise/contoso-case-study.md)。
