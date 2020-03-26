---
title: データ分類の使用を開始する (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: データ分類ダッシュボードを使用すると、組織内で検出、分類された機密データの量を確認できます。
ms.openlocfilehash: d16167f33be1858733173026b09f268d9cf67d62
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929419"
---
# <a name="know-your-data---data-classification-overview-preview"></a>データを把握する - データ分類の概要 (プレビュー)

Microsoft 365 の管理者またはコンプライアンス管理者は、組織内のコンテンツを評価してタグ付けすることにより、コンテンツの保存場所を制御し、保存場所に関わらずコンテンツを保護でき、また、組織のニーズに合わせてコンテンツを保持および削除できるようになります。 これらは、[秘密ラベル](sensitivity-labels.md)、[保持ラベル](labels.md)、および機密情報の種類の分類を適用することにより行います。 検出、評価、タグ付けを行うにはさまざまな方法がありますが、最終的には、これらのラベルの一方または両方を使用してタグ付けおよび分類された大量のドキュメントとメールが生み出される可能性があります。 保持ラベルと機密ラベルを適用した後は、テナント全体でラベルがどのように使用されているか、これらのアイテムに対してどのような操作が行われているかを確認する必要があります。 こうした内容は、データ分類のページで確認できます。具体的には次の内容を確認できます。

- 機密情報の種類として分類されたアイテムの数およびこれらの分類の種類
- Microsoft 365 および Azure Information Protection の両方で最も多く適用されている機密ラベル
- 最も多く適用されている保持ラベル
- 機密コンテンツに対してユーザーが行っているアクティビティの概要
- 機密データおよび保持されたデータの保存場所

データ分類は、**Microsoft 365 コンプライアンス センター**または **Microsoft 365 セキュリティ センター**  >  [**分類**]  >  [**データ分類**] で確認できます。

## <a name="sensitive-information-types-used-most-in-your-content"></a>コンテンツで最も多く使用されている機密情報の種類

Microsoft 365 では、社会保障番号を含むアイテムやクレジットカード番号を含むアイテムなど、機密情報の種類の定義が多数提供されています。 機密情報の種類の詳細については、「[機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)」を参照してください。

機密情報の種類カードには、組織全体で検出されたラベル付けされている機密情報の種類のうち上位のものが示されます。

![上位の機密情報の種類](../media/data-classification-sens-info-types-card.png)

特定の分類カテゴリに含まれるアイテムの数を確認するには、そのカテゴリのバーをポイントします。

![上位の機密情報の種類をポイントした際の詳細情報](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> "No data found with sensitive information" (機密情報が含まれるデータが見つかりませんでした) というメッセージがカードに表示される場合、 機密情報の種類として分類されているアイテムが組織に存在しないか、クロールされたアイテムが存在しないことを意味します。 ラベルの使用を開始するには、次を参照してください。
>- [機密ラベル](sensitivity-labels.md)
>- [保持ラベル](labels.md)
>- [機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)

## <a name="top-sensitivity-labels-applied-to-content"></a>コンテンツに適用されている上位の機密ラベル

Microsoft 365 または Azure Information Protection (AIP) のいずれかでアイテムに機密ラベルを適用すると、次の 2 つのことが起こります。

- 組織にとってのアイテムの価値を示すタグがドキュメントに埋め込まれ、そのタグはドキュメントとともにどこにでも移動します。
- タグが含まれることで、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。 エンド ポイントの保護を有効にすると、アイテムを組織の制御から離れさせないようにもできます。

機密ラベルの詳細については、「[Learn about sensitivity labels (機密ラベルの詳細)](sensitivity-labels.md)」を参照してください。

SharePoint および OneDrive にあるファイルに対応するデータがデータ分類ページに表示されるようにするには、機密度ラベルを有効にする必要があります。 詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。

機密ラベル カードには、機密レベルごとのアイテム (メールやドキュメント) の数が表示されます。

![機密ラベルの分類別のコンテンツの内訳用プレースホルダーのスクリーンショット](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> 機密ラベルをまだ作成または発行していない場合、または、いずれのコンテンツにも機密ラベルが適用されていない場合、"No sensitivity labels detected" (機密ラベルが検出されませんでした) というメッセージがこのカードに表示されます。 ラベルの使用を開始するには、次を参照してください。
>- 「[機密ラベル](sensitivity-labels.md)」または、AIPについては「[Azure Information Protection ポリシーを構成する](https://docs.microsoft.com/azure/information-protection/configure-policy)」

## <a name="top-retention-labels-applied-to-content"></a>コンテンツに適用されている上位の保持ラベル

保持ラベルは、組織内のコンテンツの廃棄を管理するために使用されます。 適用された保持ラベルは、ドキュメントが削除されるまでの期間、削除前に確認を必要とするかどうか、保持期間の有効期限、または削除できないよう記録としてマークするかどうかを制御できます。 詳細については、「[保持ラベルの概要](labels.md)」を参照してください。

最も多く適用されている保持ラベルのカードには、特定の保持ラベルが付けられているアイテムの数が表示されます。

![最も多く適用されている保持ラベル用プレースホルダーのスクリーンショット](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> "No retention labels detected" (保持ラベルが検出されませんでした) というメッセージがカードに表示される場合、保持ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。 保持ラベルの使用を開始するには、
>- 「[保持ラベルの概要](labels.md)」を参照してください。

## <a name="top-activities-detected"></a>検出された上位アクティビティ

このカードでは、機密ラベルが付けられたアイテムに対してユーザーが行う最も一般的な操作の概要が示されます。 [アクティビティ エクスプローラー](data-classification-activity-explorer.md)を使用すると、ラベル付きコンテンツおよび Windows 10 のエンドポイントにあるコンテンツでの、Microsoft 365 により追跡される 8 つの異なるアクティビティの詳細を確認できます。

> [!NOTE]
> "No activity detected" (アクティビティが検出されませんでした) というメッセージがこのカードに表示される場合、ファイルに対して行われたアクティビティがなかったか、ユーザーまたは管理者による監査が有効化されていないことを意味します。 監査ログをオンにするには、次を参照してください。
>- [セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a>場所別の機密ラベルおよび保持ラベル付きデータ

データ分類の報告の目的は、どのラベルが付いているアイテムがどこにいくつあるかを確認できるようにすることにあります。 これらのカードでは、Exchange、SharePoint、OneDrive などにあるラベル付きのアイテムの数が表示されます。

> [!NOTE]
> "No locations detected" (場所が検出されませんでした) というメッセージがこのカードに表示される場合、機密ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。 機密ラベルの使用を開始するには、次を参照してください。
>- [機密ラベル](sensitivity-labels.md)

## <a name="see-also"></a>関連項目

- [ラベル アクティビティを表示する (プレビュー)](data-classification-activity-explorer.md)
- [ラベル付きコンテンツの表示 (プレビュー)](data-classification-content-explorer.md)
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](labels.md)
- [機密情報の種類の検索基準](what-the-sensitive-information-types-look-for.md)
- [アイテム保持ポリシーの概要](retention-policies.md)
