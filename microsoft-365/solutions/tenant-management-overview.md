---
title: エンタープライズ向けのMicrosoft 365のテナント管理
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: Microsoft 365 テナントの計画、デプロイ、および継続的な運用の概要。
ms.openlocfilehash: 7a9545800c3f5f08b8094290c4173b4368caff4d
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62524215"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>エンタープライズ向けのMicrosoft 365のテナント管理

クラウド コンピューティングを使用して組織のデジタル変革へのパスを作成するには、従業員が生産性、コラボレーション、パフォーマンス、プライバシー、コンプライアンス、セキュリティに依存できる強固な基盤が必要です。

Microsoft 365 テナントを正しく構成すると、その基盤が提供され、ワーカーは作業を完了することに専念し、IT 部門は、追加のビジネス価値を提供するエンド ツー エンド ソリューションに集中できます。

このソリューションでは、次の手順でその基盤の構成について説明します。

1. テナントを決定する
2. ネットワークを最適化する
3. ID を同期し、セキュリティで保護されたサインインを適用する
4. Windows デバイス、Office クライアント、オンプレミスのOffice サーバーとデータを移行する
5. デバイスとアプリの管理を展開する

しかし、まず、テナントとは何か、また、強固な基盤を提供するテナントの外観を理解しましょう。

## <a name="a-microsoft-365-tenant-defined"></a>定義されたMicrosoft 365 テナント

Microsoft 365 テナントは、Microsoft 365のサービスと、ヨーロッパや北米などの特定の既定の場所に格納されている組織データの専用インスタンスです。 この場所は、組織のテナントを作成するときに指定します。 各Microsoft 365テナントは、個別で一意であり、他のすべてのMicrosoft 365テナントとは別です。 Microsoft 365 E3や E5 など、Microsoft から 1 つ以上の製品を購入し、それぞれに一連のライセンスを購入すると、Microsoft 365 テナントを作成します。

Microsoft 365 テナントには、Azure Active Directory (Azure AD) テナントも含まれています。これは、ユーザー アカウント、グループ、およびその他のオブジェクトのAzure ADの専用インスタンスです。 各Azure ADテナントは、個別で一意であり、他のすべてのAzure AD テナントとは別です。 組織は、Azure サブスクリプションで設定できる複数のAzure AD テナントを持つことができますが、Microsoft 365 テナントは、テナントの作成時に作成された 1 つのAzure AD テナントのみを使用できます。

次に例を示します：

![Azure AD テナントMicrosoft 365テナントの例。](../media/tenant-management-overview/tenant-management-example-tenant.png)

*テナント管理* は、Microsoft 365 テナントの計画、展開、継続的な運用です。

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>適切に設計され、運用されているテナントの属性

テナントの適切な名前と場所を超えて、クラウドの生産性アプリ&mdash;を使用したユーザー エクスペリエンスをMicrosoft TeamsやExchange Online&mdash;効果的、セキュリティ、パフォーマンスを確保するために、計画、デプロイ、管理するための追加の要素があります。

要素を次に示します。

- 正しい製品セット (サブスクリプション) とライセンスがあります。
  - 一連の製品は、ビジネス、IT、セキュリティのニーズに一致します。
  - 従業員に適切な数のライセンスがあり、スタッフの変更が予想されます。
- ネットワークの場合:
  - 正しい DNS ドメイン名を構成しました。
  - エンタープライズ ネットワークの場合は、オンサイト ワーカー用に Microsoft ネットワークへのネットワーク トラフィックを最適化しました。
  - VPN クライアントを使用しているリモート ワーカーのネットワーク トラフィックを最適化しました。
- Active Directory Domain Services (AD DS) アカウント、グループ、その他のオブジェクトを同期しました。
  - Azure AD テナント アカウントは、電子メール アドレスの正しい DNS ドメインを持つメールボックスExchange Onlineにマップされます。
  - ユーザー アカウントには、正しい購入済み製品 (Microsoft 365 E3や E5 など) から正しいライセンスが割り当てられています。
- 強力な ID とアクセス管理を構成しました。
  - パスワードレスまたは多要素認証 (MFA) でセキュリティで保護されたユーザー サインインが必要です。
  - より高いレベルのセキュリティに対してサインイン要件と制限を適用する条件付きアクセス ポリシーがあります。
- オンプレミスのOffice サーバーとそのデータがクラウド アプリに移行されているか、ハイブリッド構成で使用されています。
- Microsoft 365に組み込まれたIntuneまたは Basic Mobility and Security を使用してデバイス管理を行っています。
  - 組織所有のデバイスが登録され、管理されます。
  - 個人用デバイス用のアプリは管理されます。

これらの要素がすべて配置されたMicrosoft 365 テナントの例を次に示します。

![テナントMicrosoft 365例。](../media/tenant-management-overview/tenant-management-tenant-config.png)

この図では、Microsoft 365 テナントには次のものが含まれます。

- Microsoft 365 E3と E5 の製品とライセンス。
- 生産性アプリをMicrosoft 365します。
- 登録済みのデバイスとデバイスポリシーとアプリケーション ポリシーを使用してIntuneします。
- 同期されたユーザー アカウント (グループとその他のディレクトリ オブジェクトは表示されません)、ドメイン、条件付きアクセス ポリシーを持つAzure AD テナント。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>エンタープライズ向けのMicrosoft 365のテナント機能

次のセクションと表に、このソリューションの手順の主な機能とライセンスを示します。

### <a name="tenant"></a>Tenant

|機能|説明|ライセンス|
|---|---|---|
|複数のテナント|各Microsoft 365テナントは、個別で一意であり、他のすべてのMicrosoft 365テナントとは別です。 複数のテナントでは、テナントを管理し、ユーザーにサービスを提供する際には、制限と追加の考慮事項があります。|Microsoft 365 E3 または E5|
|テナント間でのメールボックスの移行|テナント管理者は、オンプレミス システムのインフラストラクチャの依存関係を最小限に抑えて、テナント間でメールボックスを移動できます。 これにより、メールボックスをオフボードおよびオンボードする必要が解消されます。|Microsoft 365 E3 または E5|
|Multi-Geo|テナントは、データ所在地の要件を満たすために選択した他のデータセンターの地理的な場所に保存データを格納できます。|Microsoft 365 E3 または E5|
|コア データを新しいデータセンター geo に移動する|Microsoft が新しいデータセンター geo を追加して容量とコンピューティング リソースを追加すると、コア顧客データの地域内データの所在地に関するデータセンター geo の移動を要求できます。|Microsoft 365 E3 または E5|
||||

### <a name="networking"></a>ネットワーク

|機能|説明|ライセンス|
|---|---|---|
|ネットワーク インサイト|Microsoft 365 テナントから収集されたネットワーク パフォーマンス メトリックは、オフィスの場所のネットワーク境界を設計するのに役立ちます。|Microsoft 365 E3 または E5|
|エンドポイントの更新を自動化する|クライアント PAC ファイルとネットワーク デバイスとサービスのMicrosoft 365 エンドポイントの構成と継続的な更新を自動化します。|Microsoft 365 E3 または E5|
||||

### <a name="identity"></a>ID

|機能|説明|ライセンス|
|---|---|---|
|オンプレミスの Active Directory Domain Services (AD DS) をAzure AD テナントと同期する|ユーザー アカウント、グループ、その他のオブジェクトに対してオンプレミス ID プロバイダーを活用します。|Microsoft 365 E3 または E5|
|セキュリティの既定値が適用されている MFA|サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。|Microsoft 365 E3 または E5|
|条件付きアクセスが適用されている MFA|条件付きアクセス ポリシーを使用してサインインの属性に基づいて MFA を要求します。|Microsoft 365 E3 または E5|
|リスクベースの条件付きアクセスが適用されている MFA|ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。|Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3|
|セルフサービスによるパスワードのリセット (SSPR)|ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。|Microsoft 365 E3 または E5|
||||

### <a name="migration"></a>移行

|機能|説明|ライセンス|
|---|---|---|
|Windows 10 に移行する|Windows 7 または Windows 8.1 を実行するデバイスをWindows 10 Enterpriseに移行します。|Microsoft 365 E3または E5 に含まれるWindows 10 Enterprise ライセンス|
|Microsoft 365 Apps for enterpriseに移行する|Word やPowerPointなどのOffice クライアント アプリを、新機能で更新されたクラウドからインストールされたバージョンに移行します。|Microsoft 365 E3 または E5|
|オンプレミスサーバーとデータをMicrosoft 365に移行する|Exchange メールボックス、SharePoint サイト、Skype for Business Online をクラウド サービスMicrosoft 365移行します。|Microsoft 365 E3 または E5|
||||

### <a name="device-and-app-management"></a>デバイスおよびアプリの管理

|機能|説明|ライセンス|
|---|---|---|
|Microsoft Intune|モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を提供するクラウドベースのサービス。|Microsoft 365 E3 または E5|
|基本的なモビリティとセキュリティ|この組み込みサービスを使用して、iPhone、iPad、Android、Windows電話などのユーザーのモバイル デバイスをセキュリティで保護して管理します。|Microsoft 365 E3 または E5|
||||

## <a name="next-steps"></a>次の手順

Microsoft 365 テナントを設定および管理するには、次の手順に従います。

1. [テナントを決定する](tenant-management-tenants.md)
2. [ネットワークを最適化する](tenant-management-networking.md)
3. [ID を同期し、セキュリティで保護されたサインインを適用する](tenant-management-identity.md)
4. [オンプレミスのOffice サーバーとデータを移行する](tenant-management-migration.md)
5. [デバイスとアプリの管理を展開する](tenant-management-device-management.md)

[![Microsoft 365 テナントをデプロイして管理する手順。](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

各手順では、デプロイ オプションについて説明し、結果を要約し、継続的なメンテナンス タスクを行います。

架空の代表的な多国籍組織が、Microsoft 365 テナントの要素をどのように展開したかを理解するには、[Contoso のケース スタディ](../enterprise/contoso-case-study.md)を参照してください。
