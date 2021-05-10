---
title: データ移行についての一般的な FAQ
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: コア データを新しいデータセンター geo に移動する方法に関するよく寄せられる質問 (FAQ) にOffice 365します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 46dfdddc50c62970b679a130b3cccf692648cd5c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52298054"
---
# <a name="data-move-general-faq"></a>データ移行についての一般的な FAQ

保存中の主要な顧客データを新しいデータセンター geo に移動する方法に関する一般的な質問に対する回答を次に示します。
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>移行をリクエストする対象となるのは、どんなお客様ですか?
  
新Microsoft 365 geo の対象となる国を選択した既存の商用顧客は、移行を要求できます。 このプログラムは、Microsoft 365 テナントに割り当てられた適格な国コードを持つテナントにのみ存在し、対象となるワークロードのコア顧客データを、対応する Microsoft 365 データセンター geo に移行します。 国の適格性を確認するには、「データ移動 [を要求する方法](request-your-data-move.md) 」ページを参照してください。   

## <a name="how-do-we-define-core-customer-data"></a>コア顧客データの定義方法
 
コア顧客データは、以下の用語で定義されている顧客データのサブセットをMicrosoft Online Services [します](https://aka.ms/ost)。 
- ExchangeOnline メールボックスのコンテンツ (メール本文、予定表のエントリ、メール添付ファイルのコンテンツ)
- SharePoint Online サイトのコンテンツと、そのサイト内に格納されているファイル
- OneDrive for Business にアップロードしたファイル 

## <a name="what-is-in-scope-for-teams-migration"></a>移行の対象範囲Teams。

オンライン、Exchange Online、SharePointに加OneDrive for Business。Microsoft は、Teamsデータをローカル データセンターに移行します。 
- Teams、プライベート メッセージやチャネル メッセージを含むチャット メッセージを作成します。 
- Teamsで使用される画像を表示します。 

TeamsファイルはオンラインにSharePointされTeamsチャット ファイルはオンラインにOneDrive for Business。 ボイスメール、予定表、および連絡先は、Exchange Online。 多くの場合、Exchange Online、SharePoint Online、および OneDrive for Business は、ローカル データセンター geo 内の顧客によって既に使用され、対象となる顧客国の Microsoft 365 移行プログラムの一部です。

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>移行が完了した時点で、テナントの主要な顧客データが新しい geo に保存されますか?

オンライン/Exchange Online と SharePoint OneDrive for Businessの間の共有依存関係のため、両方のサービスが移行されるまで、移行は完了したとは見なされません。 Exchange OnlineとSharePointオンライン/OneDrive for Businessは、互いに独立して別々の時間に移行する場合が多い。 顧客テナント管理者は、各サービス移行が完了するとメッセージ センターで確認を受け取り、管理センターのデータ場所カードをいつでも表示して、各サービスの保存場所にある主要な顧客データを確認できます。

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>どのように確実に移行中の顧客データを保護し、ダウンタイムが発生しないようにするのですか?
  
データの移動は、エンド ユーザーへの影響を最小限に抑えた、バック エンド サービス操作です。 影響を受け得る機能は、データの移動中と移動 [後に一覧表示されます](during-and-after-your-data-move.md)。 弊社は、Microsoft Online Servicesサービス レベル契約 [(SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) を遵守しています。そのため、移行中にユーザーが準備または監視する必要があるものは何もありません。 
  
すべてのMicrosoft 365サービスはデータセンターで同じバージョンを実行しますので、一貫性のある機能が保証されます。 このプロセス中、サービスは完全にサポートされます。
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>異なる geo に異なるサービスがあることには、どんな影響がありますか?

一部のMicrosoft 365サービスは、一部の既存の顧客と、移動プロセスの途中にある顧客に対して異なる地域に位置している場合があります。 サービスは互いに独立して実行され、このような場合はユーザー エクスペリエンスに影響はありません。 ただし、データ常駐の目的では、Exchange Online と SharePoint Online/OneDrive for Business の両方が同じデータセンター geo に移行されるまで、テナントの移行は完了と見なされません。

 ## <a name="where-is-my-core-customer-data-located"></a>コア顧客データはどこに保存されていますか?

顧客テナント管理者は、管理センターでデータの場所カードをいつでも表示して、各サービスの主要な顧客データ (特にテナント用) を確認できます。  また、新しいテナントの現在の既定の主要顧客データの参照として[、Microsoft 365](https://office.com/datamaps)対話型データセンター マップ上のデータセンター geos、データセンター、および Office 365 顧客データの場所を公開します。 顧客データの保存場所は、管理センターの [組織プロファイル] の [データの場所] セクションMicrosoft 365確認できます。  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>いつから移行をリクエストできますか?
  
データセンター geo でサポート [される時間枠については](request-your-data-move.md) 、「データ移動を要求する方法」ページを参照してください。
  
## <a name="how-can-i-request-to-be-moved"></a>どのように移行をリクエストしますか?
  
対象となるユーザーには、管理センターに[ページMicrosoft 365表示されます](https://admin.microsoft.com/)。 移行をリクエストする手順については「[データ移行をリクエストする方法](request-your-data-move.md)」をご覧ください。 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>移行をリクエストした後で自分の決定を変更できますか?
  
リクエストを送信した後に、Microsoft 側で移行プロセスからお客様を削除することはできません。
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>期限までに移行をリクエストしないと、どうなりますか?
  
オープン登録期間後の移行の要求は受け付けできません。

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>ネットワークのパフォーマンスを向上するために、データを移動したらどうなりますか?
  
データ センターへの物理的なMicrosoft 365は、ネットワーク パフォーマンスの向上を保証するものではありません。 エンド ユーザーとサービス間のネットワーク パフォーマンスに影響を与える多くの要因とMicrosoft 365があります。 このチューニングとパフォーマンスチューニングの詳細については、「ネットワーク計画とパフォーマンスチューニング for Microsoft 365」 を[参照してください](network-planning-and-performance.md)。
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>すべてのサービスは同じ日にデータを移行しますか?
 
各サービスは個別に移動し、異なる時間にデータを移動する可能性があります。
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>データを移行する時期を自分で選ぶことはできますか?
 
Microsoft が移行の具体的な日付や期間を共有することもできません。
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>データが移動される時間を共有できますか?
  
データの移動は、エンド ユーザーへの影響を最小限に抑えた、バック エンド操作です。 グローバルに運用され自動化された環境内でデータ移動を実行する必要がある複雑さ、精度、およびスケールによって、テナントまたは他の単一テナントでデータ移動が完了すると予想される場合、共有できません。 お客様のデータ移動が完了すると、お客様はメッセージ センターで、参加しているサービスごとに 1 つの確認メッセージを受信します。 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>データの移行中に、ユーザーがサービスにアクセスすると、どうなりますか?

各サービスのデータの移行中に制限される機能の詳細な一覧については「[データの移行中および移行後](during-and-after-your-data-move.md)」を参照してください。 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>移行が完了したことはどのようにわかりますか?
  
各サービスMicrosoft 365の移動が完了したという確認については、メッセージ センターで確認してください。 各サービスのデータを移動すると、完了通知が投稿され、Exchange Online、SharePoint Online、Skype for Business Online の 3 つの完了通知が表示されます。 また、管理センターの [組織プロファイル] の [データの場所] セクションを使用して、保存中の顧客データMicrosoft 365確認することもできます。  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>新しいデータセンター geo Microsoft 365の顧客ですが、サインアップすると、別の国を選択しました。 新しいデータセンター geo に移行するにはどうすればよいですか?

テナントに関連付けられているサインアップ国を変更できません。 代わりに、新しいサブスクリプションを使用して新Microsoft 365を作成し、ユーザーとデータを新しいテナントに手動で移動する必要があります。
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>移行中にメール データの移行が行Microsoft 365場合Exchange Online。

これは非常に一般的なシナリオであり、完全にサポートされています。  データセンター geos 間のクラウド移行は、オンプレミスからクラウド メールボックスへの移行に影響しません。
  
 ## <a name="can-i-pilot-some-users"></a>一部のユーザーを先に移行できますか?
  
接続をテストするために別の試用版テナントを作成することはできますが、試用版テナントと既存のテナントを統合することはできません。

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>Microsoft がデータを移動するのを待ちたくない。 新しいテナントを作成して自分で移行することはできますか?
  
だたし、プロセスは Microsoft がデータ移行を実行するときと同じようにシームレスではありません。
  
新しいデータセンター geo が利用可能になった後に新しいテナントを作成すると、新しいテナントは新しい geo でホストされます。この新しいテナントは以前のテナントとは完全に別個のものであり、すべてのユーザー メールボックス、サイトのコンテンツ、ドメイン名、その他のデータの移行をお客様自身の責任で実行していただくことになります。なお、テナント名は 1 つのテナントから別のテナントへ移行できないことに注意してください。Microsoft によって提供される移行プログラムをお待ちいただくことをお勧めします。すべての設定、データ、ユーザーのサブスクリプションの移行は、弊社にお任せください。
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>私の顧客データは新しいデータセンター geo に既に移行しました。 戻すことはできますか?
 
いいえ、できません。 新しい geo のデータセンターに移行したお客様は、元の geo に戻ることはできません。 任意の geo の顧客として、サービスの品質、パフォーマンス、およびセキュリティ コントロールに関して、これまでと同様のエクスペリエンスを得ることができます。 [Microsoft 365複数](https://aka.ms/multi-geo)地域は、一部のお客様がアドオンとして利用できます。また、1 つのテナントで複数のサテライト geo を作成し、データ常駐のコミットメントを使用してユーザー データをそれらの地域に移動できます。
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>新Microsoft 365でホストされているテナントは、国以外のユーザーが利用できますか?
  
はい。 Microsoft は、2,700 を超えるインターネット サービス プロバイダー (ISP) とのピアリング契約を締結し、世界 35 か国の 130 以上の場所でパブリック インターネット接続を備える大規模なグローバル ネットワークを維持しています。 インターネット上のどの場所にいるユーザーでも、データセンターにアクセスできます。

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>テナントが複数地域アドオン [を構成しました](https://aka.ms/multi-geo)。 引き続き、Microsoft 365 Move Program のテナントに登録して、既定の geo を変更し、サテライト地域に存在しないユーザーを新しい既定の geo に移動できますか?

はい、テナントは登録する資格がありますが、複数地域を構成した顧客ではテナント レベルの移動が完全にサポートされていないので、重要な考慮事項があります。

SharePointオンラインおよびOneDrive for Business、このプログラムを通じてテナント レベルで新しいデータセンター geo に移行することはできません。 顧客管理者は、複数地域を使用して使用可能な任意の地域に移動するように OneDrive for Business 共有を構成できますが、複数地域がテナントに対して構成されている場合、テナントの既定の場所を変更することはできません。

移行をオプトインしているお客様向け - すべての Exchange Online メールボックスを現在の既定の geo から新しいローカル データセンター geo に移動し、既定の Exchange Online 地域を更新します。 複数地域サテライト地域で構成されている EXO メールボックスは、意図した通りサテライト地域のデータ常駐を引き続き尊重するように移動されません。 

## <a name="related-topics"></a>関連項目

[コア データを新しいデータ センター geos にMicrosoft 365する](moving-data-to-new-datacenter-geos.md)

[データ移行をリクエストする方法](request-your-data-move.md)

[Microsoft 365複数地域](https://aka.ms/multi-geo)

[Microsoft 365データセンター マップ](https://office.com/datamaps)

[Microsoft 365サポート](../business-video/get-help-support.md)

[Microsoft Dynamics CRM Online の新しいデータ センター geo](/power-platform/admin/new-datacenter-regions)
  
[Azure のリージョン](https://azure.microsoft.com/regions/)