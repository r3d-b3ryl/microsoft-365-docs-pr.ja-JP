---
title: エンタープライズ向けMicrosoft 365テナント管理
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
description: ユーザーのテナントの計画、展開、および継続的なMicrosoft 365概要。
ms.openlocfilehash: 5d98f715b9233a29c8710966099667075eae0020
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573381"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>エンタープライズ向けMicrosoft 365テナント管理

クラウド コンピューティングを使用して組織のデジタル変換へのパスを作成するには、作業員が生産性、コラボレーション、パフォーマンス、プライバシー、コンプライアンス、セキュリティに頼れる基盤が必要です。

Microsoft 365 テナントの正しい構成により、その基盤が提供され、従業員は作業の完了に集中し、IT 部門は追加のビジネス価値を提供するエンドツーエンドのソリューションに集中できます。

このソリューションでは、次の手順で、その基盤の構成を説明します。

1. テナントを決定する
2. ネットワークを最適化する
3. ID を同期し、セキュリティで保護されたサインインを適用する
4. デバイス、Windows、Office、オンプレミスのサーバーとデータOffice移行する
5. デバイスとアプリの管理を展開する

しかし、最初に、テナントとは何か、また、堅固な基盤を提供するテナントの外観を理解するために少し時間を取って説明します。

## <a name="a-microsoft-365-tenant-defined"></a>定義Microsoft 365テナント

Microsoft 365テナントは、ヨーロッパや北アメリカなどの特定の既定の場所にMicrosoft 365組織データのサービスの専用インスタンスです。 この場所は、組織のテナントを作成するときに指定されます。 各Microsoft 365は、個別、一意、および他のすべてのテナントMicrosoft 365します。 Microsoft から 1 つMicrosoft 365製品 (Microsoft 365 E3 や E5 など) を購入する際に、Microsoft 365 E3 テナントを作成し、それぞれのライセンスのセットを作成します。

またMicrosoft 365テナントには Azure Active Directory (Azure AD) テナントも含まれます。これは、ユーザー アカウント、グループ、その他のオブジェクト用の Azure AD の専用インスタンスです。 各 Azure ADテナントは、個別で一意であり、他のすべての Azure テナントとADされます。 組織では、Azure サブスクリプションでセットアップできる複数の Azure AD テナントを使用できます。Microsoft 365 テナントは、テナントの作成時に作成された単一の Azure AD テナントのみを使用できます。

次に例を示します：

![Azure Microsoft 365テナントを使用してテナントAD例を示します。](../media/tenant-management-overview/tenant-management-example-tenant.png)

*テナント管理* は、テナントの計画、展開、および継続的なMicrosoft 365です。

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>十分に設計され、運用されているテナントの属性

テナントの正しい名前と場所以外にも、Microsoft Teams や Exchange Online などのクラウド生産性アプリのユーザー エクスペリエンスを効果的、安全、パフォーマンスの高いものにするための計画、展開、管理のための追加の要素があります。 &mdash; &mdash;

要素は次のとおりです。

- 製品 (サブスクリプション) とライセンスの正しいセットがあります。
  - 一連の製品は、ビジネス、IT、およびセキュリティのニーズに一致します。
  - 従業員に対して適切な数のライセンスと、スタッフの予想される変更点があります。
- ネットワークの場合:
  - 正しい名前をDNS ドメインしました。
  - エンタープライズ ネットワークの場合、オンサイト ワーカー向けに Microsoft ネットワークへのネットワーク トラフィックを最適化しました。
  - VPN クライアントを使用しているリモート ワーカーのネットワーク トラフィックを最適化しました。
- Active Directory ドメイン サービス (DS) アカウント、AD、その他のオブジェクトを同期しました。
  - Azure ADテナント アカウントは、電子メール アドレスExchange Online DNS ドメインを持つメールボックスにマップされます。
  - ユーザー アカウントには、正しい購入済み製品から適切なライセンスが割り当てられている (Microsoft 365 E3 E5 など)。
- 強力な ID とアクセス管理を構成しました。
  - パスワードレス認証または多要素認証 (MFA) によるセキュリティで保護されたユーザー サインインが必要です。
  - より高いレベルのセキュリティのためにサインイン要件と制限を適用する条件付きアクセス ポリシーがあります。
- オンプレミスのサーバー Officeデータはクラウド アプリに移行しているか、ハイブリッド構成で使用されています。
- Intune または Basic Mobility and Security を使用してデバイス管理を実行している場合は、デバイス管理Microsoft 365。
  - 組織が所有するデバイスが登録され、管理されます。
  - 個人用デバイス用のアプリは管理されます。

これらすべての要素が配置されたMicrosoft 365テナントの例を次に示します。

![テナントのMicrosoft 365例。](../media/tenant-management-overview/tenant-management-tenant-config.png)

この図では、次のMicrosoft 365を示します。

- 製品とライセンスは、Microsoft 365 E3 E5 用です。
- Microsoft 365生産性アプリ。
- Intune には、登録済みデバイスとデバイスポリシーとアプリケーション ポリシーがあります。
- ユーザー アカウントAD (グループなどのディレクトリ オブジェクトは表示されません)、ドメイン、条件付きアクセス ポリシーが同期されている Azure テナント。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>エンタープライズ向けMicrosoft 365テナント機能

次のセクションと表は、このソリューションの手順の主な機能とライセンスの一覧です。

### <a name="tenant"></a>テナント

|機能|説明|ライセンス|
|---|---|---|
|複数のテナント|各Microsoft 365は、個別、一意、および他のすべてのテナントMicrosoft 365します。 複数のテナントがある場合、それらを管理し、ユーザーにサービスを提供する際には、制限と追加の考慮事項があります。|Microsoft 365 E3 または E5|
|テナント間でのメールボックスの移行|テナント管理者は、オンプレミス システムで最小限のインフラストラクチャ依存関係を持つテナント間でメールボックスを移動できます。 これにより、オフボードメールボックスとオンボードメールボックスが不要になります。|Microsoft 365 E3 または E5|
|Multi-Geo|テナントは、データ常駐の要件を満たすために選択した他のデータセンターの地理的な場所にデータを保存できます。|Microsoft 365 E3 または E5|
|コア データを新しいデータセンター geo に移動する|Microsoft が追加の容量とコンピューティング リソース用に新しいデータセンター geo を追加すると、主要な顧客データに対する地域内データ常駐のデータセンター geo の移動を要求できます。|Microsoft 365 E3 または E5|
||||

### <a name="networking"></a>ネットワーク

|機能|説明|ライセンス|
|---|---|---|
|ネットワーク インサイト|オフィスの場所のネットワーク境界Microsoft 365を設計するために、テナントから収集されたネットワーク パフォーマンスの指標。|Microsoft 365 E3 または E5|
|エンドポイントの更新を自動化する|クライアント PAC ファイルおよびネットワーク デバイスおよびサービスMicrosoft 365エンドポイントの構成と継続的な更新を自動化します。|Microsoft 365 E3 または E5|
||||

### <a name="identity"></a>ID

|機能|説明|ライセンス|
|---|---|---|
|オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure ドメイン テナントADする|ユーザー アカウント、グループ、その他のオブジェクトのオンプレミス ID プロバイダーを活用します。|Microsoft 365 E3 または E5|
|セキュリティの既定値が適用されている MFA|サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。|Microsoft 365 E3 または E5|
|条件付きアクセスが適用されている MFA|条件付きアクセス ポリシーを使用してサインインの属性に基づいて MFA を要求します。|Microsoft 365 E3 または E5|
|リスクベースの条件付きアクセスが適用されている MFA|ユーザーが Microsoft Defender for Identity でサインインするリスクに基づいて MFA を要求します。|Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3|
|セルフサービスによるパスワードのリセット (SSPR)|ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。|Microsoft 365 E3 または E5|
||||

### <a name="migration"></a>移行

|機能|説明|ライセンス|
|---|---|---|
|Windows 10 に移行する|7 または 7 を実行するWindowsを移行Windows 8.1にWindows 10 Enterprise。|Windows 10 Enterprise E5 に含まれるMicrosoft 365 E3ライセンス|
|移行してMicrosoft 365 Apps for enterprise|Word や Officeなどのクライアント アプリPowerPoint、新しい機能で更新されたクラウドからインストールされているバージョンに移行します。|Microsoft 365 E3 または E5|
|オンプレミスのサーバーとデータをサーバーに移行Microsoft 365|クラウド サービスにExchangeメールボックス、SharePointサイト、Skype for Businessオンラインに移行Microsoft 365します。|Microsoft 365 E3 または E5|
||||

### <a name="device-and-app-management"></a>デバイスおよびアプリの管理

|機能|説明|ライセンス|
|---|---|---|
|Microsoft Intune|モバイル デバイス管理 (MDM) とモバイル アプリケーション管理 (MAM) を提供するクラウドベースのサービスで、携帯電話、タブレット、ラップトップなど、組織のアプリケーションとデバイスの使用方法を制御します。|Microsoft 365 E3 または E5|
|基本的なモビリティとセキュリティ|この組み込みサービスを使用して、iPhone、iPad、Android、Windows携帯電話など、ユーザーのモバイル デバイスをセキュリティで保護して管理します。|Microsoft 365 E3 または E5|
||||

## <a name="next-steps"></a>次の手順

これらの手順を使用して、テナントの設定と管理Microsoft 365します。

1. [テナントを決定する](tenant-management-tenants.md)
2. [ネットワークを最適化する](tenant-management-networking.md)
3. [ID を同期し、セキュリティで保護されたサインインを適用する](tenant-management-identity.md)
4. [オンプレミスのサーバーとデータOffice移行する](tenant-management-migration.md)
5. [デバイスとアプリの管理を展開する](tenant-management-device-management.md)

[![テナントを展開および管理する手順Microsoft 365します。](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

各手順では、展開オプション、結果、および継続的なメンテナンス タスクについて説明します。

架空の代表的な多国籍組織がテナントの要素を展開した方法を理解Microsoft 365 Contoso のケース スタディを[参照してください](../enterprise/contoso-case-study.md)。
