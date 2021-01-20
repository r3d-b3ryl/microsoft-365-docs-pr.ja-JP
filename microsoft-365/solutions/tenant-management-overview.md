---
title: Microsoft 365 enterprise のテナント管理
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
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントの計画、展開、および継続的な運用の概要。
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908634"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Microsoft 365 enterprise のテナント管理

クラウド コンピューティングを使用して組織のデジタル変換への道を作成するには、生産性、コラボレーション、パフォーマンス、プライバシー、コンプライアンス、セキュリティを作業者が利用できる、しっかりとした基盤が必要です。

Microsoft 365 テナントの正しい構成により、その基盤が提供され、作業の完了に集中して作業を行い、IT 部門は追加のビジネス価値を提供するエンドツーエンドのソリューションに集中できます。 

このソリューションでは、以下の手順で基礎の構成を行います。

1. テナントを決定する
2. ネットワークを最適化する
3. ID を同期し、セキュリティで保護されたサインインを適用する
4. Windows デバイス、Office クライアント、オンプレミスのサーバーとデータOffice移行する
5. デバイスとアプリの管理を展開する

しかし、最初に、テナントとは何か、そして、しっかりとした基盤を提供するテナントの外観について少し理解しましょう。

## <a name="a-microsoft-365-tenant-defined"></a>定義された Microsoft 365 テナント

Microsoft 365 テナントは、Microsoft 365 のサービスの専用インスタンスであり、ヨーロッパや北米などの特定の既定の場所に格納されている組織データです。 この場所は、組織のテナントを作成するときに指定します。 各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。 Microsoft 365 E3 や E5 など、Microsoft から 1 つ以上の製品を購入するときに Microsoft 365 テナントを作成し、それぞれのライセンスのセットを作成します。

Microsoft 365 テナントには、Azure Active Directory (Azure AD) テナントも含まれています。これは、ユーザー アカウント、グループ、その他のオブジェクト用の Azure AD の専用インスタンスです。 各 Azure ADテナントは、個別で一意であり、他のすべての Azure ADテナントとは異なります。 組織は複数の Azure AD テナントを持つ可能性があります。このテナントは Azure サブスクリプションで設定できます。Microsoft 365 テナントは、テナントの作成時に作成された Azure AD テナントを 1 つしか使用できません。 

次に例を示します：

![Azure AD テナントを持つ Microsoft 365 ADの例](../media/tenant-management-overview/tenant-management-example-tenant.png)

*テナント管理* は、Microsoft 365 テナントの計画、展開、および継続的な運用です。 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>十分に設計され運用されているテナントの属性

テナントの正しい名前と場所を超えて、Microsoft Teams や Exchange Online などのクラウド生産性向上アプリのユーザー エクスペリエンスを効果的、安全、かつ高パフォーマンスにするための追加要素を計画、展開、および管理できます。 &mdash; &mdash;

要素は次のとおりです。

- 製品 (サブスクリプション) とライセンスのセットが正しい。
  - 一連の製品は、ビジネス、IT、およびセキュリティのニーズに一致します。
  - 従業員に対して十分な数のライセンスと、スタッフの変更が予想されています。
- ネットワークの場合:
  - 正しい名前を構成DNS ドメイン。
  - エンタープライズ ネットワークの場合は、オンサイトワーカー向けに Microsoft ネットワークへのネットワーク トラフィックを最適化しました。
  - VPN クライアントを使用しているリモート ワーカーのネットワーク トラフィックを最適化しました。
- Active Directory ドメイン サービス (AD DS) アカウント、グループ、その他のオブジェクトを同期している。
  - Azure ADテナント アカウントは、電子メール アドレスの正しい DNS ドメインを持つ Exchange Online メールボックスにマップされます。
  - 購入した正しい製品 (Microsoft 365 E3 や E5 など) から、ユーザー アカウントに正しいライセンスが割り当てられている。
- 強力な ID とアクセス管理が構成されている。
  - パスワードレス認証または多要素認証 (MFA) によるセキュリティで保護されたユーザー サインインが必要です。
  - より高いレベルのセキュリティのためにサインイン要件と制限を適用する条件付きアクセス ポリシーがあります。
- オンプレミスのOfficeサーバーとそのデータがクラウド アプリに移行されたか、ハイブリッド構成で使用されています。
- Intune または Microsoft 365 に組み込みの Basic Mobility and Security を使用してデバイス管理を行っている。
  - 組織が所有するデバイスが登録および管理されている。
  - 個人用デバイス用のアプリは管理されます。

次に、これらすべての要素を配置した Microsoft 365 テナントの例を示します。

![Microsoft 365 テナントの例](../media/tenant-management-overview/tenant-management-tenant-config.png)

この図では、Microsoft 365 テナントには次が含まれます。

- Microsoft 365 E3 および E5 の製品とライセンス。
- Microsoft 365 生産性アプリ。
- 登録済みデバイスとデバイスポリシーとアプリケーション ポリシーを持つ Intune。
- Azure AD同期されたユーザー アカウント (グループおよび他のディレクトリ オブジェクトは表示されません)、ドメイン、条件付きアクセス ポリシーを持つテナントです。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Microsoft 365 enterprise のテナント機能

以下のセクションと表は、このソリューションの手順の主要な機能とライセンスの一覧です。

### <a name="tenant"></a>テナント

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| 複数のテナント | 各 Microsoft 365 テナントは、他のすべての Microsoft 365 テナントとは異なる、固有のテナントです。 複数のテナントでは、テナントを管理し、ユーザーにサービスを提供する際の制限と追加の考慮事項があります。 | Microsoft 365 E3 または E5 | 
| テナント間でのメールボックスの移行 | テナント管理者は、オンプレミス システムで最小限のインフラストラクチャの依存関係を持つテナント間でメールボックスを移動できます。 これにより、メールボックスをオフボードおよびオンボードする必要が削除されます。 | Microsoft 365 E3 または E5 | 
| Multi-Geo | テナントは、データ常駐の要件を満たすために選択した他のデータセンターの地理的位置に、保存データを保存できます。 | Microsoft 365 E3 または E5 | 
| コア データを新しいデータセンター geo に移動する | Microsoft が追加の容量とコンピューティング リソース用に新しいデータセンター geo を追加する場合、コア カスタマー データの地理的なデータ常駐のためのデータセンターの地域移動を要求できます。 | Microsoft 365 E3 または E5 | 
||||

### <a name="networking"></a>ネットワーク

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| ネットワークインサイト | Microsoft 365 テナントから収集されたネットワーク パフォーマンスメトリックは、オフィスの場所のネットワーク境界を設計するのに役立ちます。 | Microsoft 365 E3 または E5 | 
| エンドポイントの更新を自動化する | クライアント PAC ファイルとネットワーク デバイスとサービスで、Microsoft 365 エンドポイントの構成と継続的な更新を自動化します。 | Microsoft 365 E3 または E5 | 
||||

### <a name="identity"></a>ID

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure ADテナントと同期する    | ユーザー アカウント、グループ、その他のオブジェクトにオンプレミスの ID プロバイダーを活用します。 | Microsoft 365 E3 または E5 |
| セキュリティの既定値が適用されている MFA   | サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。   | Microsoft 365 E3 または E5 |
| 条件付きアクセスが適用されている MFA| 条件付きアクセス ポリシーを使用するサインインの属性に基づいて MFA を要求します。    | Microsoft 365 E3 または E5 | 
| リスクベースの条件付きアクセスが適用されている MFA   | ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。 | Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3 | 
| セルフサービスによるパスワードのリセット (SSPR)    | ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。  | Microsoft 365 E3 または E5 |
||||

### <a name="migration"></a>移行

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| Windows 10 に移行する | Windows 7 または Windows 8.1 を実行しているデバイスを Windows 10 Enterprise に移行します。 | Microsoft 365 E3 または E5 に含まれる Windows 10 Enterprise ライセンス | 
| Microsoft 365 Apps for enterprise への移行 | Word Office PowerPoint などのクライアント アプリを、新機能で更新されたクラウドからインストールされているバージョンに移行します。 | Microsoft 365 E3 または E5 | 
| オンプレミスのサーバーとデータを Microsoft 365 に移行する | Exchange メールボックス、SharePoint サイト、Skype for Business Online を Microsoft 365 クラウド サービスに移行します。 | Microsoft 365 E3 または E5 | 
||||

### <a name="device-and-app-management"></a>デバイスとアプリの管理

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| Microsoft Intune | モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を提供するクラウドベースのサービス。携帯電話、タブレット、ノート PC など、組織のアプリケーションとデバイスの使用方法を制御します。 | Microsoft 365 E3 または E5 | 
| 基本的なモビリティとセキュリティ | この組み込みサービスを使用して、iPhone、iPad、Android、Windows スマートフォンなど、ユーザーのモバイル デバイスをセキュリティで保護し、管理します。  | Microsoft 365 E3 または E5 | 
||||

## <a name="next-steps"></a>次の手順

次の手順を使用して、Microsoft 365 テナントを設定および管理します。

1. [テナントを決定する](tenant-management-tenants.md)
2. [ネットワークを最適化する](tenant-management-networking.md)
3. [ID を同期し、セキュリティで保護されたサインインを適用する](tenant-management-identity.md)
4. [オンプレミスのサーバーとデータOffice移行する](tenant-management-migration.md)
5. [デバイスとアプリの管理を展開する](tenant-management-device-management.md)

[![Microsoft 365 テナントを展開および管理する手順](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

各手順では、展開オプション、結果、および継続的なメンテナンス タスクについて説明します。

架空の代表的な多国籍組織が Microsoft 365 テナントの要素を展開した方法を理解するには、Contoso 社のケース スタディを [参照してください](../enterprise/contoso-case-study.md)。
