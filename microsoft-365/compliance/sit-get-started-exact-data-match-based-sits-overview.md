---
title: 完全なデータ一致に基づく機密情報の種類の使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 厳密なデータ一致ベースの機密情報の種類の作成の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a9fc1af50c329b96ff77108698c8bbf952813f7f
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359494"
---
# <a name="get-started-with-exact-data-match-based-sensitive-information-types"></a>完全なデータ一致に基づく機密情報の種類の使用を開始する

## <a name="applies-to"></a>適用対象 

- [新しいエクスペリエンス](sit-create-edm-sit-unified-ux-workflow.md)
- [クラシック エクスペリエンス](sit-create-edm-sit-classic-ux-workflow.md)

完全なデータ一致 (EDM) ベースの機密情報の種類 (SIT) を作成して使用できるようにするのは、多フェーズ プロセスです。 既存のクラシック エクスペリエンスまたは PowerShell を使用して *、新しい**エクスペリエンス* を使用できます。 この記事は、2 つのエクスペリエンスの違いを理解するのに役立ち、ニーズに合ったエクスペリエンスを選ぶのに役立ちます。

EDM SIT は、次の場合に使用できます。

- Microsoft Purview データ損失防止
- 自動ラベル付け (サービス側とクライアント側)
- Microsoft Purview インサイダー リスク管理 ポリシー
- Microsoft Purview 電子情報開示
- Microsoft Purview インサイダー リスク管理
- Microsoft Defender for Cloud Apps



## <a name="before-you-begin"></a>はじめに

これらの記事の概念と用語について理解します。

- [機密情報の種類に関する詳細情報](sensitive-information-type-learn-about.md)
- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md)

## <a name="supported-regions"></a>サポートされる地域

正確なデータ一致は、次のリージョンで使用できます。

- アジア太平洋
- オーストラリア
- ブラジル
- カナダ
- ヨーロッパ
- フランス
- ドイツ
- インド
- 日本
- 韓国
- ノルウェー
- 南アフリカ
- スイス
- アラブ首長国連邦
- 英国
- 米国
- US DoD
- US GCC
- US GCCH

Microsoft [365 のお客様](../enterprise/o365-data-locations.md) のデータが保存される場所と、同じ記事のデータ センターの都市の場所を参照する手順に従って、テナントが保存データをホストしているリージョンを確認できます。

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

この記事で説明されているタスクを実行するには、全体管理者、コンプライアンス管理者、または Exchange Online の管理者である必要があります。 DLP アクセス許可の詳細については、「[アクセス許可](data-loss-prevention-policies.md#permissions)」を参照してください。

完全なライセンス情報については、 [データ損失防止サービスの説明](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business) を参照してください

## <a name="portal-links-for-your-subscription"></a>サブスクリプションのポータルリンク

|ポータル|世界中の GCC|GCC-High|DOD|
|---|---|---|---|
|Office SCC|compliance.microsoft.com|scc.office365.us|scc.protection.apps.mil|
|Microsoft 365 Defender ポータル|security.microsoft.com|security.microsoft.us|security.apps.mil|
|Microsoft Purview コンプライアンス ポータル|compliance.microsoft.com|compliance.microsoft.us|compliance.apps.mil|

## <a name="new-edm-experience"></a>新しい EDM エクスペリエンス

新しい EDM エクスペリエンスは、EDM スキーマと EDM 機密情報の種類ウィザードの機能を 1 つのユーザー エクスペリエンスに組み合わせたものです。 新しいエクスペリエンスでは、次のものが追加されます。

### <a name="simplified-workflow"></a>ワークフローの簡略化

新しいエクスペリエンスでは、スキーマと SIT は 1 つのユーザー エクスペリエンスを介して作成されます。つまり、クリック数が減り、プライマリ要素を既定の SIT にマッピングし、ルールの既定の信頼レベルにマッピングするためのガイダンスが向上します。

作成プロセスで EDM SIT の状態を確認する必要がある場合は、UI で新しいエクスペリエンスがレポートされます。

- まだアップロードされていないデータ
- データアップロード率
- データアップロードの完了
- インデックス作成の完了
- データのアップロードに失敗しました
- データ インデックス作成に失敗しました


### <a name="automated-schema-and-sit-creation"></a>自動化されたスキーマと SIT の作成

新しいエクスペリエンスでは、同じヘッダー値と十分な行 (10 から 20) の代表的なデータを持つサンプル データ ファイルをシステムに提供できます。 システムは形式を検証し、ヘッダーに基づいてスキーマを作成します。 次に、スキーマ内のプライマリ フィールドを識別し、プライマリ フィールドに関連付けるのに最適な SIT を推奨します。 ファイルをアップロードしない場合は、UI に同じ値を手動で入力できます。

> [!IMPORTANT]
> 機密ではないが、実際の機密データと同じ形式のサンプル データ値を必ず使用してください。 実際の機密情報テーブルと同様に、サンプル データ ファイルをアップロードしても暗号化およびハッシュ化されないため、機密でないデータを使用することが不可欠です。 サンプル データ ファイルのデータは、EDM SIT が作成された後は保持されず、アクセスできません。

システムは、プライマリ フィールドごとに 1 つずつ、EDM SIT 検出規則を生成します。 プライマリ フィールドの検出に基づいて、システムは他のすべてのフィールドを裏付けとなる証拠として使用して、高および中信頼ルールを作成します。 必要に応じて、信頼度の低いルールを追加できます。 

### <a name="additional-guardrails-to-ensure-better-performance"></a>パフォーマンスを向上させるために追加の guardrails

<!--As the Azure-based EDM cloud service leverages a shared infrastructure, a misconfigured EDM SIT that triggers excessive EDM lookups could impact EDM performance for other customers if it wasn't controlled. This is prevented by throttling instances where EDM is misconfigured in a way that would cause excessive lookups.--> 

システムは、 *緩やかに定義* された SIT と呼ばれる広範な値を検出する SIT にマップされたプライマリ フィールドが見つかると警告します。  これにより、探しているコンテンツの種類に関連しない多数の文字列に対して検索が実行される可能性があります。 これらの種類の SIT とプライマリ フィールドの間のマッピングでは、誤った負の結果になり、パフォーマンスが低下する可能性があります。

> [!NOTE]
> すべての個人識別番号を検索するカスタムの SIT のように、 *緩やかに定義された SIT* には、検出されたアイテムの変動性を高める検出ルールがあります。 米国社会保障番号のような *厳密に定義された SIT* には、狭く明確に定義された項目のセットのみを検出できる検出ルールがあります。 

また、選択したプライマリ フィールドの値が多数の行で複数回発生した場合にも、警告が表示されます。 これにより、多数の結果セットが返されて処理され、タイムアウトになる可能性があります。タイムアウトにより、検出が欠落し、パフォーマンスが低下する可能性があります。


## <a name="choosing-the-right-edm-sit-creation-experience-for-you"></a>適切な EDM SIT 作成エクスペリエンスを選択する

新しいエクスペリエンスとクラシック エクスペリエンスを前後に切り替えることができますが、ニーズがこれら 4 つのユース ケースの 1 つ以上に該当しない限り、新しいエクスペリエンスを使用することをお勧めします。 

1. このセクションを読む
1. 使用するエクスペリエンスを選択する
1. 目的のエクスペリエンスの [次の手順](#next-steps) のリンクを選択します。

### <a name="you-want-to-map-multiple-edm-sits-to-the-same-schema"></a>複数の EDM SITS を同じスキーマにマップする

EDM では、最大 10 個のスキーマを作成できます。 新しいエクスペリエンスを使用して EDM SIT を作成するたびに、新しいスキーマが作成されます。 これにより、EDM スキーマと EDM SIT の間で 1 対 1 のマッピングが行われます。 新しいエクスペリエンスでは、複数の SIT を同じスキーマにマッピングすることはできません。

### <a name="you-need-to-create-or-manage-more-than-10-edm-sits"></a>10 を超える EDM SIT を作成または管理する必要がある

 新しいエクスペリエンスでは、同じスキーマへの複数の SIT のマッピングがサポートされていないため、10 個の EDM SITS の作成と管理に制限されます。 クラシック エクスペリエンスでは、複数の EDM SIT を同じスキーマにマップできるため、10 個を超える EDM SIT を使用できます。 新しいフローを使用して、11 番目の EDM スキーマを作成しようとして、10 個を超える EDM SIT を表示できない場合、エラーが発生します。

### <a name="you-need-to-specify-the-name-of-your-edm-schema"></a>EDM スキーマの名前を指定する必要があります

EDM SIT スキーマの名前を指定する必要がある場合は、クラシック エクスペリエンスを使用して作成および管理する必要があります。 新しいエクスペリエンスではスキーマが自動的に作成されるため、スキーマにカスタム名を付ける機会はありません。 自動生成された名前は、EDM SIT 名と単語 *スキーマ* の連結です。 たとえば、EDM SIT 名が *PatientNumber* の場合、スキーマ名は *PatientNumberschema* になります。

### <a name="you-need-to-edit-edm-schemas-that-were-created-in-the-classic-experience"></a>クラシック エクスペリエンスで作成された EDM スキーマを編集する必要があります

クラシック エクスペリエンスを使用して作成されたスキーマ、または PowerShell を使用して XML ファイルとしてアップロードされたすべてのスキーマは、新しいエクスペリエンスでは表示または管理できません。

## <a name="next-steps"></a>次の手順

- [厳密なデータ一致の機密情報の種類の新しいエクスペリエンスを作成する](sit-create-edm-sit-unified-ux-workflow.md)

or

- [厳密なデータ一致の機密情報の種類のクラシック エクスペリエンスを作成する](sit-create-edm-sit-classic-ux-workflow.md)

## <a name="see-also"></a>関連項目

- [完全なデータ一致に基づく機密情報の種類の詳細](sit-learn-about-exact-data-match-based-sits.md)
- [完全なデータ一致に基づく機密情報の種類のソース データをエクスポートする](sit-get-started-exact-data-match-export-data.md#export-source-data-for-exact-data-match-based-sensitive-information-type)
- [厳密なデータ一致の機密情報の種類のワークフローの新しいエクスペリエンスを作成する](sit-create-edm-sit-unified-ux-workflow.md)
- [厳密なデータ一致の機密情報の種類のワークフロークラシック エクスペリエンスを作成する](sit-create-edm-sit-classic-ux-workflow.md)