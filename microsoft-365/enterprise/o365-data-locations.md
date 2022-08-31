---
title: Microsoft 365 データの場所
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 08/30/2022
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Microsoft 365 の顧客データの保存場所を世界全体で確認する
ms.openlocfilehash: b786892b99e2b67114c34006c77f2e394cba6f45
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67467923"
---
# <a name="where-your-microsoft-365-customer-data-is-stored"></a>Microsoft 365 顧客データの保存場所

次の表は、Microsoft のすべてのグローバル クラウドの場所で、Microsoft 365 サービスの顧客データが保存されている場所を示しています。 請求先住所の国の場所を展開して、各サービスの顧客データが保存される場所を確認します。

ビジネスが欧州連合にある場合、詳細については、「[欧州連合のデータの場所](EU-data-storage-locations.md)」を参照してください。

お客様には、Microsoft 365 管理者センターの **[設定]**  >  **[組織の設定]**  > <a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank"> **[組織プロファイル]** タブの</a> >  **[データの場所]** でテナント固有のデータの場所情報が表示されるはずです。 [新しい地域への移行を要求した](request-your-data-move.md) 場合、移行中に一部のデータが以前の地域に一時的に保存されていることがあっても、Microsoft 365 管理センターのデータの場所情報には新しい地域だけが表示されることがあります。

新しい Microsoft 365 テナントは、そのテナントの最初のサブスクリプションに関連付けられたトランザクションの国に基づいて既定で Geo に設定されます。

お客様の保存データの保存場所に関する契約上のコミットメントに関する情報は、 [Microsoft 製品およびサービスデータ保護補遺 (DPA)](https://www.microsoft.com/licensing/docs/view/Microsoft-Products-and-Services-Data-Protection-Addendum-DPA)に記載されています。

Azure Active Directory データの場所については、「 [Azure のデータ所在地](https://azure.microsoft.com/global-infrastructure/data-residency/#overview)」を参照してください。

請求先住所がヨーロッパ以外にあり、Office 365 Educationサブスクリプションをお持ちである場合、OST の 「顧客データの場所」セクションにかかわらず、Microsoft は、Office 365 テナントをプロビジョニングし、データを転送し、データをヨーロッパ内または北米内の任意の場所に保存することができます。  請求先住所がヨーロッパにあり、Office 365 Education サブスクリプションをお持ちである場合、OST の 「Rest for Core Online Services の顧客データの場所」セクションにかかわらず、Microsoft は、お客様のOffice 365テナントをプロビジョニングし、データを転送し、欧州連合内の任意の場所に保存する場合があります。

## <a name="faq"></a>FAQ

### <a name="how-does-microsoft-define-data"></a>Microsoft はどのようにデータを定義するのですか?
<details><summary>クリックして展開</summary>

Microsoft セキュリティ センターで[さまざまな種類のデータの定義](https://go.microsoft.com/fwlink/p/?linkid=864390)を確認してください。 [プライバシーとセキュリティの使用条件](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all)で、Microsoft は顧客データ/お客様のデータに関して契約上のコミットメントを行います。 Microsoft は、[プライバシーとセキュリティの使用条件](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all)に従ってお客様の地域内でのみ保管されている顧客データをコア カスタマー データと呼びます。

</details>

### <a name="where-are-the-exact-addresses-of-the-data-centers"></a>データ センターの正確な所在地はどこですか?

<details><summary>クリックして展開</summary>

Microsoft は、データ センターの正確な所在地を開示しません。 このポリシーは、データ センター施設のセキュリティを強化するために確立されました。  ただし、都市の場所は記載しています。 詳細については、「[データ センターの場所](o365-data-locations.md#data-center-locations)」を参照してください。

</details>

### <a name="does-the-location-of-your-customer-data-have-a-direct-impact-on-your-end-users-experience"></a>顧客データの場所は、エンドユーザーのエクスペリエンスに直接影響を与えますか?
<details><summary>クリックして展開</summary>

Microsoft 365 のパフォーマンスは、データ センターの場所までのユーザーの距離に単純に比例するわけではありません。 Microsoft は、グローバル クラウド ネットワーク、グローバル クラウド インフラストラクチャ、Microsoft 365 サービス アーキテクチャにおいて継続的な投資を行っており、顧客データがどこに保存されているかに関係なく、単一で一貫性のあるエクスペリエンスをユーザーに提供します。 ユーザーにパフォーマンスの問題が発生している場合は、それらを詳細にトラブルシューティングする必要があります。 Microsoft は、[Office サポート Web サイト](./network-planning-and-performance.md)で、エンドユーザーのパフォーマンスを計画および最適化するためのガイダンスを Microsoft 365 の顧客向けに公開しています。

</details>

### <a name="how-does-microsoft-help-me-comply-with-my-national-regional-and-industry-specific-regulations"></a>Microsoft は、国、地域、業界固有の規制にどのように準拠していますか?
<details><summary>クリックして展開</summary>

個人のデータの収集と使用を管理する国、地域、業界固有の要件への準拠を支援するために、Microsoft 365 は、あらゆるグローバル クラウド生産性プロバイダーの最も包括的なコンプライアンス製品を提供します。 Microsoft トラスト センターの [Microsoft Purview](https://go.microsoft.com/fwlink/p/?linkid=862317) セクションで、[コンプライアンスの提供](/compliance/regulatory/offering-home)とその他の詳細を確認してください。 また、特定の Microsoft 365プラン では、データの管理、法的要件および規制要件への準拠、データに対して実行される操作ンの監視に役立つ追加のコンプライアンス ソリューションが提供されます。

</details>

### <a name="who-can-access-your-data-and-according-to-what-rules"></a>誰がどの規則に従ってデータにアクセスできますか?
<details><summary>クリックして展開</summary>

 Microsoft は、承認されていないユーザーによる不適切なアクセスや使用からお客様のデータを保護するための強力な対策を実施しています。 これには、Microsoft の担当者や下請業者によるアクセスの制限、および顧客データに対する政府の要求に対応するための要件を慎重に定義することが含まれます。 ただし、いつでも理由を問わず、お客様自身の顧客データにアクセスできます。 詳細については、[Microsoft セキュリティ センター](https://go.microsoft.com/fwlink/p/?linkid=864392)をご覧ください。

</details>

### <a name="does-microsoft-access-your-data"></a>Microsoft は、お客様のデータにアクセスしますか?
<details><summary>クリックして展開</summary>

Microsoft は、顧客データへの自社アクセスを意図的に制限しながら、ほとんどの Microsoft 365 操作を自動化します。 これにより、Microsoft 365 を規模に応じて管理し、顧客データに対する内部脅威のリスクに対処できます。 既定では、Microsoft のエンジニアには継続的な管理者権限も、Microsoft 365 の顧客データへのアクセス権もありません。 Microsoft のエンジニアは、限られた期間、顧客データに制限され記録された状態でアクセスできます。ただし、通常のサービス運用に必要な場合、Microsoft 上級管理職のメンバー (カスタマー ロックボックス機能のライセンスを取得しているお客様の場合はお客様) によって承認された場合のみです。

</details>

### <a name="how-does-microsoft-secure-your-data"></a>Microsoft は、お客様のデータをどのように保護していますか?
<details><summary>クリックして展開</summary>

Microsoft は、お客様の情報を安全な状態で保護できるように、信頼性の高いポリシー、コントロールとシステムを Microsoft 365 に組み込んでいます。 詳細については、Microsoft セキュリティ センターの[「Microsoft 365 セキュリティ」のセクション](https://go.microsoft.com/fwlink/p/?linkid=864393)を確認してください。

</details>

### <a name="does-microsoft-365-encrypt-your-data"></a>Microsoft 365 では、データは暗号化されるのですか?
<details><summary>クリックして展開</summary>

Microsoft 365 は、保存中および転送中の顧客データを暗号化するサービス側テクノロジを使用します。 保存中の顧客データの場合、Microsoft 365 はボリューム レベルおよびファイル レベルの暗号化を使用します。 転送中の顧客データの場合、Microsoft 365 は、トランスポート レイヤー セキュリティ (TLS) やインターネット プロトコル セキュリティ (IPsec) など、データ センター間およびクライアントとサーバー間の通信に複数の暗号化テクノロジを使用します。 Microsoft 365 には、顧客により管理される暗号化機能も含まれています。

</details>

### <a name="where-can-i-find-data-residency-information-for-microsoft-azure"></a>Microsoft Azure のデータ常駐情報はどこで入手できますか?
<details><summary>クリックして展開</summary>

Microsoft Azure のデータ常駐情報については、[地域別に利用可能な製品](https://go.microsoft.com/fwlink/p/?linkid=2093451)ページを確認してください。

</details>

### <a name="what-are-multi-geo-capabilities-in-microsoft-365"></a>Microsoft 365 の複数地域機能とは何ですか?
<details><summary>クリックして展開</summary>

[複数地域機能](https://go.microsoft.com/fwlink/p/?linkid=872033) を使用すると、ユーザーは主要な顧客データを Microsoft 365 クラウドの利用可能な場所に保存しておくことができます。

</details>  

### <a name="what-services-support-multi-geo"></a>複数地域機能をサポートするサービスは何ですか?
<details><summary>クリックして展開</summary>

[Multi-Geo](https://go.microsoft.com/fwlink/p/?linkid=872033) は、Exchange Online、OneDrive for Business、SharePoint Online および Teams で使用できます。

</details>

### <a name="why-do-i-see-my-microsoft-365-service-requests-for-my-data-at-rest-connecting-to-servers-in-countries-outside-of-my-region"></a>地域外の国のサーバーに保存され接続している私のデータについて、Microsoft 365 サービス要求に直面しなければならない理由は何ですか?
<details><summary>クリックして展開</summary>

場合によっては、お客様の要求は、データが保存されている場所とは異なる地域のサーバーによって処理される場合があります。 これは、ネットワーク ルーティングの決定によって、要求処理のために別のサーバーが選択される場合に発生しますが、しかしこのような場合、データは新しい保存場所に移動されません。

</details>

### <a name="what-are-the-exceptions-for-intune-data-locations"></a>Intune データの保存場所については、どのような例外がありますか?
<details><summary>クリックして展開</summary>

Microsoft は、次の場合を除いて、指定された地域外に Intune の顧客データを保存しません。

- Microsoft は、顧客サポートを提供したり、サービスのトラブルシューティングを行ったり、法的要件に準拠したりする必要があります。
- ユーザーは、次のような用途を含む顧客データの保存を可能にするアカウントを構成します。
  - 地球規模のキャッシュ サービスを提供し、世界中に顧客データを保存する、コンテンツ配信ネットワーク (CDN) など、グローバルに動作するように設計された機能。
  - ディレクトリ データをグローバルに保存できる、Azure Active Directory (Azure AD)。この内容は、米国 (Azure AD データは米国のみに保存されます)、または欧州 (Azure AD データは欧州または米国に保存されています) の Azure AD の展開には適用されません。
  - 通常、顧客データは米国に保存されますが、プレビュー、ベータ、およびその他のプレリリース サービスについては、グローバルに保存することができます。

いずれにしても、Microsoft は、顧客やそのエンドユーザーが顧客データにアクセスできるような地域機能を制御したり制限したりすることはありません。 同様に、他のサービスの顧客データがその後 Intune に統合される場合、元の顧客データは、他のサービス独自の Geo コミットメント (存在する場合) に従って引き続き保存されます。Intune に統合された顧客データのコピーのみが、Intune の指定された Geo に保存されます。

</details>

### <a name="what-are-the-considerations-for-microsoft-viva-data-locations"></a>Microsoft Viva 用のデータの場所についてはどのような配慮が必要ですか?
<details><summary>クリックして展開</summary>

- Viva コネクション
  - ダッシュボード、リソース、デスクトップ アプリのデータは、SharePoint Online に保存されます。
  - フィードには、SharePoint Online (ニュース)、ストリーム (SharePoint Online に静止画として保存)、Yammer (Yammer に静止画として保存) のコンテンツがあります。
- Viva インサイト
  - 個人用アプリのデータ所在地は、ユーザーのメールボックスの場所に基づくものです。
  - マネージャー/リーダーまた アドバンスト のデータ領域は、個々のユーザーではなく、テナントのプライマリ リージョンによって決定されます。

</details>

## <a name="data-center-locations"></a>データ センターの場所

次の表では、さまざまなサービスのデータの場所を定義します。 サービスの場所を決定する場合は、次の表を参照してください。

### <a name="data-center-geographies"></a>データ センターの地域

次の地域地域では、保存データを格納できます。 顧客データの保存場所は変更される場合があります。

| 地域地域 | 顧客データを保存できる場所 |
| --- | --- |
| 地域地理 1 – EMEA (ヨーロッパ、中東、アフリカ) | オーストリア、フィンランド、フランス、アイルランド、オランダ |
| 地域地理 2 – アジア太平洋 | 香港特別行政区、日本、マレーシア、シンガポール、韓国 |
| 地域地理 3 - アメリカ | ブラジル、チリ、米国 |

## <a name="countryregion-specific-data-center-city-locations"></a>国/地域固有のデータ センターの都市の場所

国/地域固有のデー タセンターの場合、以下は顧客データが保存されている都市を定義します。

| 国 | 都市 |
| --- | --- |
| オーストラリア | シドニー、メルボルン |
| ブラジル | リオ、カンピナス |
| カナダ | ケベックシティ、トロント |
| 欧州連合 | オーストリア (ウィーン)、フィンランド (ヘルシンキ)、フランス (パリ、マルセイユ)、アイルランド (ダブリン)、オランダ (アムステルダム) |
| フランス | パリ、マルセイユ |
| ドイツ | フランクフルト、ベルリン |
| インド | チェンナイ、ムンバイ、プネ |
| 日本 | 大阪、東京 |
| カタール | ドーハ |
| 韓国 | 釜山、ソウルl |
| ノルウェー | オスロ、スタヴァンゲル |
| 南アフリカ | ケープタウン、ヨハネスブルグ |
| スウェーデン | Gävle、Sandviken、Staffanstorp |
| スイス | ジュネーブ、ズリック |
| アラブ首長国連邦 | ドバイ、アブダビ |
| 英国 | ダーラム、ロンドン、カーディフ |
| 米国 |  ボイドトン、シャイアン、シカゴ、デモイン、クインシー、サンアントニオ、サンタクララ、サンノゼ |

新しい Microsoft 365 テナントは、そのテナントの最初のサブスクリプションに関連付けられた請求先住所の国に基づいて既定で地域機能に設定されます。 既存の Office 365 サービスの顧客データの保存場所を確認する場所は、Office 365 管理センターの [設定] | [組織プロファイル] | [データ場所のカード] で、テナント固有データの場所情報を閲覧してください。 または、ビジネスの拠点となる国を下のリストから展開して、今すぐ Microsoft 365 サービスの使用を開始する場合に顧客データが保存される場所を検索してください。

## <a name="afghanistan"></a>アフガニスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="aland-islands"></a>オーランド諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="albania"></a>アルバニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="algeria"></a>アルジェリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="american-samoa"></a>米領サモア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="andorra"></a>アンドラ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="angola"></a>アンゴラ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="anguilla"></a>アンギラ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="antarctica"></a>南極大陸
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="antigua-and-barbuda"></a>アンティグア バーブーダ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="argentina"></a>アルゼンチン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="armenia"></a>アルメニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="aruba"></a>アルバ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="australia"></a>オーストラリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | オーストラリア |
| OneDrive for Business | オーストラリア |
| SharePoint Online | オーストラリア |
| Microsoft Teams | オーストラリア |
| Office Online &amp; Mobile | オーストラリア |
| EOP | オーストラリア |
| Intune | オーストラリア |
| Planner | オーストラリア |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | オーストラリア |
| Stream | オーストラリア |
| Whiteboard | オーストラリア |
| フォーム | 米国 |
| Viva コネクション | オーストラリア |
| Viva トピック | オーストラリア |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | オーストラリア |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="austria"></a>オーストリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="azerbaijan"></a>アゼルバイジャン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bahamas"></a>バハマ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bahrain"></a>バーレーン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bangladesh"></a>バングラデシュ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="barbados"></a>バルバドス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="belarus"></a>ベラルーシ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="belgium"></a>ベルギー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="belize"></a>ベリーズ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="benin"></a>ベナン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bermuda"></a>バミューダ諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bhutan"></a>ブータン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bolivia"></a>ボリビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bonaire"></a>ボネール島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bosnia-and-herzegovina"></a>ボスニア・ヘルツェゴビナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="botswana"></a>ボツワナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bouvet-island"></a>ブーベ島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="brazil"></a>ブラジル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | ブラジル |
| OneDrive for Business | ブラジル |
| SharePoint Online | ブラジル |
| Microsoft Teams | ブラジル |
| Office Online &amp; Mobile | ブラジル |
| EOP | ブラジル |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | ブラジル |
| Stream | ブラジル |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | ブラジル |
| Viva トピック | ブラジル |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | ブラジル |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="british-indian-ocean-territory"></a>イギリス領インド洋地域
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="british-virgin-islands"></a>英領バージン諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="brunei"></a>ブルネイ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="bulgaria"></a>ブルガリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="burkina-faso"></a>ブルキナファソ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="burundi"></a>ブルンジ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cambodia"></a>カンボジア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cameroon"></a>カメルーン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="canada"></a>カナダ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | カナダ |
| OneDrive for Business | カナダ |
| SharePoint Online | カナダ |
| Microsoft Teams | カナダ |
| Office Online &amp; Mobile | カナダ |
| EOP | カナダ |
| Intune | 米国 |
| Planner | カナダ |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | カナダ |
| Stream | カナダ |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | カナダ |
| Viva トピック | カナダ |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | カナダ |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cape-verde"></a>カーボベルデ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cayman-islands"></a>ケイマン諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="central-african-republic"></a>中央アフリカ共和国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="chad"></a>チャド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="chile"></a>チリ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="china"></a>中国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="christmas-island"></a>クリスマス島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cocos-keeling-islands"></a>ココス諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="colombia"></a>コロンビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="comoros"></a>コモロ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="congo-brazzaville"></a>コンゴ民主共和国 (ブラザビル)
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="congo-kinshasa"></a>コンゴ共和国、(キンシャサ)
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cook-islands"></a>クック諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="costa-rica"></a>コスタリカ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cote-divoire"></a>コートジボワール
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="croatia"></a>クロアチア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="curacao"></a>キュラソー島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="cyprus"></a>キプロス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="czech-republic"></a>チェコ共和国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="denmark"></a>デンマーク
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="djibouti"></a>ジブチ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="dominica"></a>ドミニカ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="dominican-republic"></a>ドミニカ共和国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="ecuador"></a>エクアドル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="egypt"></a>エジプト
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="el-salvador"></a>エルサルバドル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="equatorial-guinea"></a>赤道ギニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="eritrea"></a>エリトリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="estonia"></a>エストニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="ethiopia"></a>エチオピア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="falkland-islands-malvinas"></a>フォークランド (マルビナス) 諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="faroe-islands"></a>フェロー諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="federated-states-of-micronesia"></a>ミクロネシア連邦
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="fiji"></a>フィジー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | オーストラリア |
| OneDrive for Business | オーストラリア |
| SharePoint Online | オーストラリア |
| Microsoft Teams | オーストラリア |
| Office Online &amp; Mobile | オーストラリア |
| EOP | オーストラリア |
| Intune | オーストラリア |
| Planner | オーストラリア |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | オーストラリア |
| Stream | オーストラリア |
| Whiteboard | オーストラリア |
| フォーム | 米国 |
| Viva コネクション | オーストラリア |
| Viva トピック | オーストラリア |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | オーストラリア |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="finland"></a>フィンランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="france"></a>フランス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | フランス |
| OneDrive for Business | フランス |
| SharePoint Online | フランス |
| Microsoft Teams | フランス |
| Office Online &amp; Mobile | フランス |
| EOP | フランス |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合 |
| OneNote サービス | フランス |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | フランス |
| Viva トピック | フランス |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | フランス |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="french-guiana"></a>フランス領ギアナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="french-polynesia"></a>フランス領ポリネシア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="french-southern-territories"></a>フランス領極南諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="gabon"></a>ガボン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="gambia"></a>ガンビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="georgia"></a>ジョージア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="germany"></a>ドイツ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | ドイツ |
| OneDrive for Business | ドイツ |
| SharePoint Online | ドイツ |
| Microsoft Teams | ドイツ |
| Office Online &amp; Mobile | ドイツ |
| EOP | ドイツ |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合 |
| OneNote サービス | ドイツ |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | ドイツ |
| Viva トピック | ドイツ |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | ドイツ |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="ghana"></a>ガーナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="gibraltar"></a>ジブラルタル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="greece"></a>ギリシャ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="greenland"></a>グリーンランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="grenada"></a>グレナダ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guadeloupe"></a>グアドループ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guam"></a>グアム
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guatemala"></a>グアテマラ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guernsey"></a>ガーンジー島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guinea"></a>ギニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guinea-bissau"></a>ギニアビサウ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="guyana"></a>ガイアナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="haiti"></a>ハイチ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="heard-and-mcdonald-islands"></a>ハード・マクドナルド諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="herzegovina"></a>ヘルツェゴビナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="holy-see-vatican-city-state"></a>バチカン市国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="honduras"></a>ホンジュラス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="hong-kong-sar"></a>香港
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="hungary"></a>ハンガリー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="iceland"></a>アイスランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="india"></a>インド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | インド |
| OneDrive for Business | インド |
| SharePoint Online | インド |
| Microsoft Teams | インド |
| Office Online &amp; Mobile | インド |
| EOP | インド |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | インド |
| Stream | インド |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | インド |
| Viva トピック | インド |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | インド |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="indonesia"></a>インドネシア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="iraq"></a>イラク
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="ireland"></a>アイルランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="isle-of-man"></a>マン島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="israel"></a>イスラエル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="italy"></a>イタリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="jamaica"></a>ジャマイカ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="japan"></a>日本
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 日本 |
| OneDrive for Business | 日本 |
| SharePoint Online | 日本 |
| Microsoft Teams | 日本 |
| Office Online &amp; Mobile | 日本 |
| EOP | 日本 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | 日本 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 日本 |
| Stream | 日本 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 日本 |
| Viva トピック | 日本 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | 日本 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="jersey"></a>ジャージー島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="jordan"></a>ヨルダン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="kazakhstan"></a>カザフスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="kenya"></a>ケニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="kiribati"></a>キリバス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="south-korea"></a>韓国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 韓国 |
| OneDrive for Business | 韓国 |
| SharePoint Online | 韓国 |
| Microsoft Teams | 韓国 |
| Office Online &amp; Mobile | 韓国 |
| EOP | 韓国 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 韓国 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 韓国 |
| Viva トピック | 韓国 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | 韓国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="kosovo"></a>コソボ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="kuwait"></a>クウェート
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="kyrgyzstan"></a>キルギスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="laos"></a>ラオス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="latvia"></a>ラトビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="lebanon"></a>レバノン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="lesotho"></a>レソト
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="liberia"></a>リベリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="libya"></a>リビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="liechtenstein"></a>リヒテンシュタイン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | スイス |
| OneDrive for Business | スイス |
| SharePoint Online | スイス |
| Microsoft Teams | スイス |
| Office Online &amp; Mobile | スイス |
| EOP | スイス |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合 |
| OneNote サービス | スイス |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | スイス |
| Viva トピック | スイス |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | スイス |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="lithuania"></a>リトアニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="luxembourg"></a>ルクセンブルク
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="madagascar"></a>マダガスカル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="malawi"></a>マラウイ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="malaysia"></a>マレーシア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="maldives"></a>モルディブ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mali"></a>マリ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="malta"></a>マルタ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="marshall-islands"></a>マーシャル諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="martinique"></a>マルティニーク島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mauritania"></a>モーリタニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mauritius"></a>モーリシャス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mayotte"></a>マイヨット
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mexico"></a>メキシコ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="moldova"></a>モルドバ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="monaco"></a>モナコ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mongolia"></a>モンゴル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="montenegro"></a>モンテネグロ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="montserrat"></a>モントセラト
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="morocco"></a>モロッコ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="mozambique"></a>モザンビーク
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="myanmar"></a>ミャンマー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="namibia"></a>ナミビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="nauru"></a>ナウル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="nepal"></a>ネパール
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="netherlands"></a>オランダ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="netherlands-antilles"></a>オランダ領アンティル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="new-caledonia"></a>ニューカレドニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="new-zealand"></a>ニュージーランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | オーストラリア |
| OneDrive for Business | オーストラリア |
| SharePoint Online | オーストラリア |
| Microsoft Teams | オーストラリア |
| Office Online &amp; Mobile | オーストラリア |
| EOP | オーストラリア |
| Intune | オーストラリア |
| Planner | オーストラリア |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | オーストラリア |
| Stream | オーストラリア |
| Whiteboard | オーストラリア |
| フォーム | 米国 |
| Viva コネクション | オーストラリア |
| Viva トピック | オーストラリア |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | オーストラリア |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="nicaragua"></a>ニカラグア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="niger"></a>ニジェール
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="nigeria"></a>ナイジェリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="niue"></a>ニウエ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="norfolk-island"></a>ノーフォーク島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="northern-mariana-islands"></a>北マリアナ諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="norway"></a>ノルウェー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | ノルウェー |
| OneDrive for Business | ノルウェー |
| SharePoint Online | ノルウェー |
| Microsoft Teams | ノルウェー |
| Office Online &amp; Mobile | ノルウェー |
| EOP | ノルウェー |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | ノルウェー |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| ホワイトボード | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| フォーム | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | ノルウェー |
| Viva トピック | ノルウェー |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | ノルウェー |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |

</p></details>

## <a name="oman"></a>オマーン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="pakistan"></a>パキスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="palau"></a>パラオ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="palestinian-authority"></a>パレスチナ自治政府
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="panama"></a>パナマ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="papua-new-guinea"></a>パプアニューギニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="paraguay"></a>パラグアイ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="peru"></a>ペルー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="philippines"></a>フィリピン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="pitcairn"></a>ピトケアン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="poland"></a>ポーランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="portugal"></a>ポルトガル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="puerto-rico"></a>プエルトリコ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="qatar"></a>カタール
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | カタール* |
| OneDrive for Business | カタール* |
| SharePoint Online | カタール* |
| Exchange Online Protection | カタール* |
| Microsoft Defender for Office P1 | カタール* |
| Microsoft Teams | カタール* |
| Office for the Web | カタール* |
| Office for Mobile | カタール* |
| OneNote サービス | カタール* |
| Stream | カタール* |
| Whiteboard | カタール* |
| Viva コネクション | カタール* |
| Viva インサイト - Personal Insights | カタール* |
| Viva トピック | カタール* |
| Azure Active Directory | 欧州連合 |
| Microsoft Dataverse for Teams | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Power Automate Desktop | 欧州連合 |
| Teams 用 Power Virtual Agent | 欧州連合 |
| Viva インサイト - Mgr / Leader / Advanced | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Yammer | 欧州連合 |
| Forms | 米国 |

*保存時の顧客データをExchange Online、SharePoint Online、またはOneDrive for Businessに格納するサービス、またはローカルに展開するすべてのサービス。
</p></details>

## <a name="republic-of-macedonia"></a>マケドニア共和国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="runion"></a>レユニオン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="romania"></a>ルーマニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="russian-federation"></a>ロシア連邦
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="rwanda"></a>ルワンダ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-helena"></a>セントヘレナ島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-kitts-and-nevis"></a>セントクリストファー ネイビス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-lucia"></a>セントルシア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-martin"></a>サンマルタン島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-pierre-and-miquelon"></a>サンピエール島/ミクロン島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-vincent-and-the-grenadines"></a>セントビンセント グレナディーン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saint-barthlemy"></a>サンバルテルミー
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="samoa"></a>サモア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="san-marino"></a>サンマリノ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="sao-tome-and-principe"></a>サントメ・プリンシペ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="saudi-arabia"></a>サウジアラビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="senegal"></a>セネガル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="serbia"></a>セルビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="seychelles"></a>セーシェル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="sierra-leone"></a>シエラレオネ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="singapore"></a>シンガポール
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="sint-maarten"></a>シント・マールテン島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="slovakia"></a>スロバキア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="slovenia"></a>スロベニア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="solomon-islands"></a>ソロモン諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="somalia"></a>ソマリア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="south-africa"></a>南アフリカ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 南アフリカ |
| OneDrive for Business | 南アフリカ |
| SharePoint Online | 南アフリカ |
| Microsoft Teams | 南アフリカ |
| Office Online &amp; Mobile | 南アフリカ |
| EOP | 南アフリカ |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | 南アフリカ |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 南アフリカ |
| Viva トピック | 南アフリカ |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | 南アフリカ |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
 </p></details>

## <a name="south-georgia-and-the-south-sandwich-islands"></a>サウスジョージア サウスサンドウィッチ諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="spain"></a>スペイン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 欧州連合 |
| OneDrive for Business | 欧州連合 |
| SharePoint Online | 欧州連合 |
| Microsoft Teams | 欧州連合 |
| Office Online &amp; Mobile | 欧州連合 |
| EOP | 欧州連合 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合  |
| OneNote サービス | 欧州連合 |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 欧州連合 |
| Viva トピック | 欧州連合 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 欧州連合 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="sri-lanka"></a>スリランカ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="suriname"></a>スリナム
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="svalbard-and-jan-mayen-islands"></a>スバールバル諸島、ヤンマイエン島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="swaziland"></a>スワジランド
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="sweden"></a>スウェーデン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | スウェーデン |
| OneDrive for Business | スウェーデン |
| SharePoint Online | スウェーデン |
| Microsoft Teams | スウェーデン |
| Office Online &amp; Mobile | スウェーデン |
| EOP | スウェーデン |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合 |
| OneNote サービス | スウェーデン |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | スウェーデン |
| Viva トピック | スウェーデン |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | スウェーデン |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="switzerland"></a>スイス
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | スイス |
| OneDrive for Business | スイス |
| SharePoint Online | スイス |
| Microsoft Teams | スイス |
| Office Online &amp; Mobile | スイス |
| EOP | スイス |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合 |
| OneNote サービス | スイス |
| Stream | 欧州連合 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | スイス |
| Viva トピック | スイス |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | スイス |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="taiwan"></a>台湾
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="tajikistan"></a>タジキスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="united-republic-of-tanzania"></a>タンザニア連合共和国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="thailand"></a>タイ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="timor-leste"></a>ティモール・レステ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="togo"></a>トーゴ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="tokelau"></a>トケラウ諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="tonga"></a>トンガ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="trinidad-and-tobago"></a>トリニダード・トバゴ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="tunisia"></a>チュニジア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="turkey"></a>トルコ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="turkmenistan"></a>トルクメニスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="turks-and-caicos-islands"></a>タークス カイコス諸島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="tuvalu"></a>ツバル
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="us-virgin-islands"></a>ヴァージン諸島 (米国)
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="uganda"></a>ウガンダ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="ukraine"></a>ウクライナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="united-arab-emirates"></a>アラブ首長国連邦
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | アラブ首長国連邦 |
| OneDrive for Business | アラブ首長国連邦 |
| SharePoint Online | アラブ首長国連邦 |
| Microsoft Teams | アラブ首長国連邦 |
| Office Online &amp; Mobile | アラブ首長国連邦 |
| EOP | アラブ首長国連邦 |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | アラブ首長国連邦 |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | アラブ首長国連邦 |
| Viva トピック | アラブ首長国連邦 |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | アラブ首長国連邦 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
 </p></details>

## <a name="united-kingdom"></a>英国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 英国 |
| OneDrive for Business | 英国 |
| SharePoint Online | 英国 |
| Microsoft Teams | 英国 |
| Office Online &amp; Mobile | 英国 |
| EOP | 英国 |
| Intune | 欧州連合 |
| Planner | 欧州連合 |
| Sway | 米国 |
| Yammer | 欧州連合 |
| OneNote サービス | 英国 |
| Stream | 英国 |
| Whiteboard | 欧州連合 |
| Forms | 欧州連合 |
| Viva コネクション | 英国 |
| Viva トピック | 英国 |
| Viva ラーニング | 欧州連合 |
| Viva インサイト - 個人用 | 英国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 欧州連合 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="united-states"></a>米国
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="uruguay"></a>ウルグアイ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 3 - 米国 |
| OneDrive for Business | グローバル地域 3 - 米国 |
| SharePoint Online | グローバル地域 3 - 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | グローバル地域 3 - 米国 |
| EOP | グローバル地域 3 - 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 3 - 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 3 - 米国 |
| Viva トピック | グローバル地域 3 - 米国 |
| Viva ラーニング | グローバル地域 3 - 米国 |
| Viva インサイト - 個人用 | グローバル地域 3 - 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 3 - 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="us-minor-outlying-islands"></a>合衆国領有小離島
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="uzbekistan"></a>ウズベキスタン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="vanuatu"></a>バヌアツ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="venezuela"></a>ベネズエラ
<details><summary>クリックして展開</summary><p>
| サービス | 場所 |
| --- | --- |
| Exchange Online | 米国 |
| OneDrive for Business | 米国 |
| SharePoint Online | 米国 |
| Microsoft Teams | 米国 |
| Office Online &amp; Mobile | 米国 |
| EOP | 米国 |
| Intune | 米国 |
| Planner | 米国 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | 米国 |
| Stream | 米国 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | 米国 |
| Viva トピック | 米国 |
| Viva ラーニング | 米国 |
| Viva インサイト - 個人用 | 米国 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | 米国 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="vietnam"></a>ベトナム
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="wallis-and-futuna-islands"></a>ウォリス フツナ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 2 – アジア太平洋 |
| OneDrive for Business | グローバル地域 2 – アジア太平洋 |
| SharePoint Online | グローバル地域 2 – アジア太平洋 |
| Microsoft Teams | グローバル地域 2 – アジア太平洋 |
| Office Online &amp; Mobile | グローバル地域 2 – アジア太平洋 |
| EOP | グローバル地域 2 – アジア太平洋 |
| Intune | グローバル地域 2 – アジア太平洋 |
| Planner | グローバル地域 2 – アジア太平洋 |
| Sway | 米国 |
| Yammer | 米国 |
| OneNote サービス | グローバル地域 2 – アジア太平洋 |
| Stream | グローバル地域 2 – アジア太平洋 |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 2 – アジア太平洋 |
| Viva トピック | グローバル地域 2 – アジア太平洋 |
| Viva ラーニング | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 個人用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 2 – アジア太平洋 |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="western-sahara"></a>西サハラ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="yemen"></a>イエメン
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | 米国 |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="zambia"></a>ザンビア
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>

## <a name="zimbabwe"></a>ジンバブエ
<details><summary>クリックして展開</summary><p>

| サービス | 場所 |
| --- | --- |
| Exchange Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneDrive for Business | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| SharePoint Online | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Microsoft Teams | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Office Online &amp; Mobile | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| EOP | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Intune | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Planner | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Sway | 米国 |
| Yammer | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| OneNote サービス | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Stream | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Whiteboard | 米国 |
| Forms | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva コネクション | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva トピック | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva ラーニング | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 個人用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - 管理者/リーダー AAD 組織データ専用 | グローバル地域 1 – EMEA (ヨーロッパ、中東、アフリカ) |
| Viva インサイト - サードパーティの人事データのみを使用するマネージャー/リーダー | 米国 |
| Viva インサイト - 上級 | 米国 |
</p></details>
