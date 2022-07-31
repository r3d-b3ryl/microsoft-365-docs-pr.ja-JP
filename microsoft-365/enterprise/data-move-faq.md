---
title: データ移行についての一般的な FAQ
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 05/31/2022
audience: ITPro
ms.topic: faq
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: コア データを新しいOffice 365データセンター geo に移動する方法に関してよく寄せられる質問 (FAQ) に対する回答を確認します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3164612238010e72eb02510e1264cca528b80f38
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "66994233"
---
# <a name="data-move-general-faq"></a>データ移行についての一般的な FAQ

保存時のコア顧客データを新しいデータセンター geo に移動する方法に関する一般的な質問に対する回答を次に示します。

### <a name="what-customers-are-eligible-to-request-a-move"></a>移行をリクエストする対象となるのは、どんなお客様ですか?
<details><summary>クリックして展開</summary>

新しいデータセンター geo の対象となる国を選択した既存の Microsoft 365 商用顧客は、引っ越しを要求できます。 このプログラムは、対象となるワークロードの保存時のコア顧客データを対応する Microsoft 365 データセンター geo に移行するために、対象となる国コードが Microsoft 365 テナントに割り当てられているテナントにのみ存在します。 国の資格を確認するために [データ移動を要求する方法](request-your-data-move.md) に関する説明を参照してください。

</details>

### <a name="how-do-we-define-core-customer-data"></a>Core Customer Data を定義する方法
<details><summary>クリックして展開</summary>

コア顧客データとは、 [Microsoft Online Services の利用規約](https://aka.ms/ost)で定義されている顧客データのサブセットを指す用語です。

- ExchangeOnline メールボックスのコンテンツ (メール本文、予定表のエントリ、メール添付ファイルのコンテンツ)
- SharePoint Online サイトのコンテンツと、そのサイト内に格納されているファイル
- OneDrive for Business にアップロードしたファイル

</details>

### <a name="what-is-in-scope-for-teams-migration"></a>Teams 移行のスコープは何ですか?
<details><summary>クリックして展開</summary>

Exchange Online、SharePoint Online、OneDrive for Businessに加えて、Microsoft は Teams データをローカル データセンターに移行します。

- プライベート メッセージやチャネル メッセージを含む Teams チャット メッセージ。
- チャットで使用される Teams イメージ。

Teams ファイルは SharePoint Online に保存され、Teams チャット ファイルはOneDrive for Businessに保存されます。 ボイスメール、予定表、連絡先はExchange Onlineに格納されます。 多くの場合、Exchange Online、SharePoint Online、およびOneDrive for Businessは、ローカル データセンター geo のお客様によって既に使用されており、対象となるお客様の国の Microsoft 365 移行プログラムの一部でもあります。

</details>

### <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>テナントのコア顧客データが新しい geo に保存されるように、移行はどの時点で完了しますか?
<details><summary>クリックして展開</summary>

Exchange Onlineと SharePoint Online/OneDrive for Businessの間の共有依存関係のため、両方のサービスが移行されるまで、移行は完了したと見なすことができません。 Exchange Onlineと SharePoint Online/OneDrive for Businessは、多くの場合、別々の時間に移行し、相互に独立して移行します。 顧客テナント管理者は、各サービスの移行が完了するとメッセージ センターで確認を受け取り、管理 センターのデータの場所カードをいつでも表示して、各サービスの保存場所にあるコア顧客データを確認できます。

</details>

### <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>どのように確実に移行中の顧客データを保護し、ダウンタイムが発生しないようにするのですか?
<details><summary>クリックして展開</summary>

データの移動は、エンド ユーザーへの影響を最小限に抑えたバックエンド サービス操作です。 影響を受ける可能性がある機能は、 [データの移動中と移動後](during-and-after-your-data-move.md)に一覧表示されます。 Microsoft [Online Services サービス レベル アグリーメント (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) に準拠しているため、お客様が移動中に準備したり監視したりする必要はありません。

すべての Microsoft 365 サービスは、データセンターで同じバージョンを実行するため、一貫した機能が保証されます。 このプロセス中、サービスは完全にサポートされます。

</details>

### <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>異なる geo に異なるサービスがあることには、どんな影響がありますか?
<details><summary>クリックして展開</summary>

Microsoft 365 サービスの一部は、一部の既存の顧客と、移動プロセスの途中にある顧客のために、異なる地域に配置される場合があります。 Microsoft のサービスは互いに独立して実行されます。この場合、ユーザー エクスペリエンスに影響はありません。 ただし、データ常駐の目的では、Exchange Onlineと SharePoint Online/OneDrive for Businessの両方が同じデータセンター geo に移行されるまで、テナントの移行を完了と見なすことはできません。

</details>

### <a name="where-is-my-core-customer-data-located"></a>コア 顧客データはどこにありますか?
<details><summary>クリックして展開</summary>

カスタマー テナント管理者は、管理 センターのデータの場所カードをいつでも表示して、サービスごとの保存場所 (特にテナント用) のコア顧客データを確認できます。 また、[Microsoft 365 対話型データセンター マップ](https://office.com/datamaps)上のデータセンター geo、データセンター、Office 365顧客データの場所も、新しいテナントの保存場所にある現在の既定のコア 顧客データの参照として公開します。 保存している顧客データの場所は、Microsoft 365 管理センターの組織プロファイルの [データの場所] セクションで確認できます。

</details>

### <a name="when-will-i-be-able-to-request-a-move"></a>いつから移行をリクエストできますか?
<details><summary>クリックして展開</summary>

データセンター geo でサポートされている期間については、「 [データ移動を要求する方法](request-your-data-move.md) 」ページを参照してください。

</details>

### <a name="how-can-i-request-to-be-moved"></a>どのように移行をリクエストしますか?
<details><summary>クリックして展開</summary>

対象となるお客様には、[Microsoft 365 管理センター](https://admin.microsoft.com/)にページが表示されます。 移行をリクエストする手順については「[データ移行をリクエストする方法](request-your-data-move.md)」をご覧ください。

</details>

### <a name="can-i-change-my-selection-after-requesting-a-move"></a>移行をリクエストした後で自分の決定を変更できますか?
<details><summary>クリックして展開</summary>

リクエストを送信した後に、Microsoft 側で移行プロセスからお客様を削除することはできません。

</details>

### <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>期限までに移行をリクエストしないと、どうなりますか?
<details><summary>クリックして展開</summary>

オープン登録期間を過ぎると、移行の要求を受け入れることができません。

</details>

### <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>ネットワークのパフォーマンスを向上するために、データを移動したらどうなりますか?
<details><summary>クリックして展開</summary>

Microsoft 365 データセンターへの物理的な近接性は、ネットワーク パフォーマンスの向上を保証するものではありません。 エンド ユーザーと Microsoft 365 サービスの間のネットワーク パフォーマンスに影響を与える要因とコンポーネントは多数あります。 このチューニングとパフォーマンスチューニングの詳細については、 [Microsoft 365 のネットワーク計画とパフォーマンスのチューニングに関するページを](network-planning-and-performance.md)参照してください。

</details>

### <a name="do-all-the-services-move-their-data-on-the-same-day"></a>すべてのサービスは同じ日にデータを移行しますか?
<details><summary>クリックして展開</summary>

各サービスは個別に移動し、異なる時間にデータを移動する可能性があります。

</details>

### <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>データを移行する時期を自分で選ぶことはできますか?
<details><summary>クリックして展開</summary>

Microsoft が移行の具体的な日付や期間を共有することもできません。

</details>

### <a name="can-you-share-when-my-data-will-be-moved"></a>データが移動されるタイミングを共有できますか?
<details><summary>クリックして展開</summary>

データの移動はバックエンド操作であり、エンド ユーザーへの影響は最小限です。 グローバルに運用され、自動化された環境内でデータ移動を実行する必要がある複雑さ、精度、スケールにより、テナントまたはその他の単一テナントに対してデータ移動が完了すると予想される場合、共有を禁止しています。 お客様のデータ移動が完了すると、お客様はメッセージ センターで、参加しているサービスごとに 1 つの確認メッセージを受信します。

</details>

### <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>データの移行中に、ユーザーがサービスにアクセスすると、どうなりますか?
<details><summary>クリックして展開</summary>

各サービスのデータの移行中に制限される機能の詳細な一覧については「[データの移行中および移行後](during-and-after-your-data-move.md)」を参照してください。

</details>

### <a name="how-do-i-know-the-move-is-complete"></a>移行が完了したことはどのようにわかりますか?
<details><summary>クリックして展開</summary>

各サービスのデータの移動が完了したことを確認するには、Microsoft 365 メッセージ センターをご覧ください。 各サービスのデータが移動されると、完了通知が投稿されるので、Exchange Online、SharePoint Online、Skype for Business Online の 3 つの完了通知が表示されます。 また、Microsoft 365 管理センターの組織プロファイルの下にある [データの場所] セクションを使用して、保存中の顧客データの場所を確認することもできます。

</details>

### <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>新しいデータセンター geo の 1 つである Microsoft 365 のお客様ですが、サインアップ時に別の国を選択しました。 新しいデータセンター geo に移行するにはどうすればよいですか?
<details><summary>クリックして展開</summary>

テナントに関連付けられているサインアップ国を変更することはできません。 代わりに、新しいサブスクリプションを使用して新しい Microsoft 365 テナントを作成し、ユーザーとデータを新しいテナントに手動で移動する必要があります。

</details>

### <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>Exchange Onlineの移行中に Microsoft 365 への電子メール データの移行を行っている場合はどうなりますか?
<details><summary>クリックして展開</summary>

これは非常に一般的なシナリオであり、完全にサポートされています。 データセンター geo 間のクラウド移行は、オンプレミスからクラウド メールボックスへの移行を妨げることはありません。

</details>

### <a name="can-i-pilot-some-users"></a>一部のユーザーを先に移行できますか?
<details><summary>クリックして展開</summary>

接続をテストするために別の試用版テナントを作成することはできますが、試用版テナントと既存のテナントを統合することはできません。

</details>

### <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Microsoft が自分のデータを移動するのを待ちたくない。 新しいテナントを作成して自分で移行することはできますか?
<details><summary>クリックして展開</summary>

だたし、プロセスは Microsoft がデータ移行を実行するときと同じようにシームレスではありません。

新しいデータセンター geo が利用可能になった後に新しいテナントを作成すると、新しいテナントは新しい geo でホストされます。この新しいテナントは以前のテナントとは完全に別個のものであり、すべてのユーザー メールボックス、サイトのコンテンツ、ドメイン名、その他のデータの移行をお客様自身の責任で実行していただくことになります。なお、テナント名は 1 つのテナントから別のテナントへ移行できないことに注意してください。Microsoft によって提供される移行プログラムをお待ちいただくことをお勧めします。すべての設定、データ、ユーザーのサブスクリプションの移行は、弊社にお任せください。

</details>

### <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>私の顧客データは新しいデータセンター geo に既に移行しました。 戻すことはできますか?
<details><summary>クリックして展開</summary>

いいえ、できません。 新しい geo のデータセンターに移行したお客様は、元の geo に戻ることはできません。 任意の geo の顧客として、サービスの品質、パフォーマンス、およびセキュリティ コントロールに関して、これまでと同様のエクスペリエンスを得ることができます。 [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) は、アドオンとして一部のお客様が利用でき、1 つのテナントで複数のサテライト geo を作成し、データ常駐コミットメントを持つそれらの geo にユーザー データを移動できます。

</details>

### <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>新しいデータセンターでホストされている Microsoft 365 テナントは、国外のユーザーが利用できますか?
<details><summary>クリックして展開</summary>

はい。 Microsoft は、2,700 を超えるインターネット サービス プロバイダー (ISP) とのピアリング契約を結び、世界 35 か国の 130 を超える場所にパブリック インターネット接続を持つ大規模なグローバル ネットワークを維持しています。 インターネット上のどの場所にいるユーザーでも、データセンターにアクセスできます。

</details>

### <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>テナントで Multi Geo アドオンが構成されています。 Microsoft 365 Move Program で引き続きテナントに登録できますか?既定の geo を変更し、サテライト リージョンにないユーザーを新しい既定の geo に移動するには
<details><summary>クリックして展開</summary>

はい。テナントは登録の対象となりますが、 [複数地域](https://aka.ms/multi-geo)を構成しているお客様はテナント レベルの移動が完全にサポートされていないため、重要な考慮事項があります。

SharePoint Online とOneDrive for Businessは、このプログラムを使用してテナント レベルで新しいデータセンター geo に移行することはできません。 顧客管理者は、複数地域を使用して使用可能な任意のリージョンに移動するようにOneDrive for Business共有を構成できますが、テナントに対して Multi-Geo を構成した後は、テナントの既定の場所を変更することはできません。

移行をオプトインするお客様の場合は、すべてのExchange Onlineメールボックスを現在の既定の地域から新しいローカル データセンター geo に移動し、既定のExchange Onlineリージョンを更新します。 マルチ Geo サテライトリージョンで構成された EXO メールボックスは、お客様が意図したとおりにサテライト リージョンのデータ所在地を尊重し続けるために移動することはありません。  Multi Geo 構成を使用する顧客の Teams チャット サービス テナント移行は、Exchange Onlineと同様に動作します。

</details>

### <a name="i-have-public-folders-deployed-in-my-tenant-what-will-be-the-impact-on-public-folder-access-during-or-after-the-move"></a>テナントにパブリック フォルダーが展開されています。 移動中または移動後にパブリック フォルダーへのアクセスに与える影響は何ですか?
<details><summary>クリックして展開</summary>

パブリック フォルダーの移動中または移動後に、エンド ユーザーがパブリック フォルダーにアクセスしても影響はありません。 ただし、すべてのパブリック フォルダー メールボックスが同じリージョンに移動されるまで、Exchange 管理 センター ツールでパブリック フォルダーを管理できない場合があります。 詳細については [、この記事](https://aka.ms/pfxrf) を参照してください。

</details>

### <a name="related-topics"></a>関連項目

[新しい Microsoft 365 データセンター geo へのコア データの移動](moving-data-to-new-datacenter-geos.md)

[データ移行をリクエストする方法](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Microsoft 365 対話型データセンター マップ](https://office.com/datamaps)

[Microsoft 365 サポート](../admin/get-help-support.md)

[Microsoft Dynamics CRM Online の新しいデータ センター geo](/power-platform/admin/new-datacenter-regions)

[Azure のリージョン](https://azure.microsoft.com/regions/)
