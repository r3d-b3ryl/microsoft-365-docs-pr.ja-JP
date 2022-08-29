---
title: コンテンツ エクスプローラーの使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: コンテンツ エクスプローラーにより、ラベル付きアイテムをネイティブに表示することができます。
ms.openlocfilehash: d00d8febe5c30b438d77e3c9b82b6a8bb6011812
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67360459"
---
# <a name="get-started-with-content-explorer"></a>コンテンツ エクスプローラーの使用を開始する

コンテンツ エクスプローラーを使用すると、概要ページで要約されたアイテムをネイティブに表示することができます。

## <a name="prerequisites"></a>前提条件

ライセンス要件については、「[Information Protection: データ分類分析: 概要コンテンツとアクティビティ エクスプローラー](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)」 を参照してください。

### <a name="permissions"></a>アクセス許可

[コンテンツ エクスプローラー] タブにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。 

**Microsoft 365 の役割グループ**

- 全体管理者
- コンプライアンス管理者
- セキュリティ管理者
- コンプライアンス データ管理者

> [!IMPORTANT]
> これらの役割グループのメンバーシップでは、コンテンツ エクスプローラーでアイテムの一覧を表示したり、コンテンツ エクスプローラーでアイテムの内容を表示したりすることができません。

> [!IMPORTANT]
> グローバル管理者のみが、コンプライアンス ポータルで他のユーザーに対してアクセス許可を管理または割り当てることができます。 詳細については、「[Microsoft Purview コンプライアンス センターのアクセス許可](microsoft-365-compliance-center-permissions.md)」 を参照してください。
> 
### <a name="required-permissions-to-access-items-in-content-explorer"></a>コンテンツ エクスプローラーでアイテムにアクセスするために必要なアクセス許可

コンテンツ エクスプローラーへのアクセスは、スキャンしたファイルのコンテンツを読み取ることができるため、厳しく制限されています。

> [!IMPORTANT]
> これらのアクセス許可は、アイテムにローカルに割り当てられるアクセス許可の代わりに、コンテンツの表示を許可します。 

コンテンツ エクスプローラーへのアクセスを許可する 2 つの役割があり、<a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">Microsoft Purview コンプライアンス ポータル</a>を使用して許可されます。

- **Content Explorer リスト ビューアー**: この役割グループのメンバーシップを使用すると、リスト ビューで各項目とその場所を表示できます。`data classification list viewer` のロールは、この役割グループに事前に割り当てられています。

- **Content Explorer コンテンツ ビューアー**: この役割グループのメンバーシップを使用すると、リスト内の各項目の内容を表示できます。この役割グループには、`data classification content viewer` の役割が事前に割り当てられています。

コンテンツ エクスプローラーにアクセスするために使用するアカウントには、1 つまたは両方の役割のグループがある必要があります。 独立した役割のグループがあり、累積ではありません。 たとえば、アイテムおよびそれらの場所のみ表示する機能をアカウントに付与する場合は、コンテンツ エクスプローラーのリスト ビューアーの権利を付与します。 その同じアカウントでリスト内のアイテムのコンテンツも表示できるようにするには、コンテンツ エクスプローラーのコンテンツ ビューアーの権利も付与します。

また、役割の一方または両方をカスタム役割グループに割り当てて、コンテンツ エクスプローラーへのアクセスをカスタマイズすることもできます。

グローバル管理者は、必要なコンテンツ エクスプローラーのリスト ビューアーとコンテンツ エクスプローラーのコンテンツ ビューアーの役割グループ メンバーシップを割り当てることができます。

#### <a name="roles-and-role-groups-in-preview"></a>プレビュー段階の [役割と役割グループ]

プレビューには、アクセス制御を微調整するためにテストできる役割と役割グループがあります。

プレビュー段階の該当する役割の一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)」を参照してください。

- Information Protection 管理者
- Information Protection アナリスト
- Information Protection 調査員
- Information Protection 閲覧者

プレビュー段階の該当する役割グループの一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

- 情報保護
- Information Protection レベル
- Information Protection アナリスト
- Information Protection 調査担当者
- Information Protection 閲覧者

## <a name="content-explorer"></a>コンテンツ エクスプローラー

コンテンツ エクスプローラーは、機密ラベル、保持ラベルまたは組織で機密情報の種類として分類されているアイテムの現在のスナップショットです。

### <a name="sensitive-information-types"></a>機密情報の種類

[DLP ポリシー](dlp-learn-about-dlp.md)は、**機密情報の種類** として定義されている機密情報を保護するのに役立ちます。 Microsoft 365 には、さまざまな地域にわたる[多くの一般的な機密情報の種類に対する定義](sensitive-information-type-entity-definitions.md)が含まれていて、すぐに使用できる状態になっています。 たとえば、クレジット カード番号、銀行口座番号、国内 ID 番号などです。

### <a name="sensitivity-labels"></a>秘密度ラベル

[機密ラベル](sensitivity-labels.md)は、組織に対するアイテムの価値を示すタグです。 手動で、または自動的に適用することができます。 適用すると、ラベルがドキュメントに埋め込まれ、ドキュメントがどこへ移動されてもラベルはドキュメントにしたがって移動します。 機密ラベルによって、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。

SharePoint および OneDrive にあるファイルに対応するデータがデータ分類ページに表示されるようにするには、機密度ラベルを有効にする必要があります。 詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。

### <a name="retention-labels"></a>保持ラベル

[保持ラベル](retention.md)を使用すると、ラベル付けされたアイテムの保持期間、およびアイテムを削除する前に行う手順を定義できます。 手動で、またはポリシーを使用して自動的に適用することができます。 組織が法的要件および規制要件を遵守するのに役立ちます。

### <a name="how-to-use-content-explorer"></a>コンテンツ エクスプローラーの使用方法

1. **Microsoft Purview コンプライアンス ポータル**  > **[データ分類]** > **[コンテンツ エクスプローラー]** の順に開きます。
2. ラベルの名前または機密情報の種類が分かる場合は、それをフィルター ボックスに入力することができます。
3. 交互に、ラベルの種類を展開してリストからラベルを選択し、アイテムを参照することができます。
4. [**すべての場所**] の下で場所を選択して、アイテムのフォルダー構造をドリルダウンします。
5. ダブルクリックして、コンテンツ エクスプローラーでネイティブにアイテムを開きます。

### <a name="export"></a>エクスポート
**エクスポート** コントロールは、ウィンドウのフォーカスの一覧を含む .csv ファイルを作成します。

![データ分類エクスポート コントロール。](../media/data_classification_export_control.png)


> [!NOTE]
> コンテンツ エクスプローラーでカウントが更新されるまで、最大 *7日* かかる場合があります。

### <a name="filter"></a>Filter

Exchange またはTeams フォルダー、SharePoint、OneDrive サイトなどの場所をドリルダウンするとき、**[フィルター]** ツールが表示されます。

![コンテンツ エクスプローラー検索ツール。](../media/data_classification_search_tool.png)

検索ツールの範囲は、**[すべての場所 ]** ウィンドウに表示される内容です。また、検索できる対象は、選択した場所によって異なります。 

**Exchange** または **Teams** が選択された場所である場合、`user@domainname.com` のようにメールボックスの完全なメール アドレスを検索できます。

**SharePoint** または **OneDrive** が選択された場所である場合、サイト名、フォルダー、ファイルをドリルダウンすると、検索ツールが表示されます。 

以下を検索できます。

|値|例  |
|---------|---------|
|完全なサイト名    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|ファイル名    |    `RES_Resume_1234.txt`     |
|ファイル名の最初のテキスト| `RES`|
|ファイル名の下線文字 (_) 以降のテキスト|`Resume` または `1234`| 
|ファイル拡張子|`txt`|


## <a name="see-also"></a>関連項目

- [秘密度ラベルの詳細](sensitivity-labels.md)
- [アイテム保持ポリシーと保持ラベルの詳細](retention.md)
- [機密情報の種類のエンティティ定義.md](sensitive-information-type-entity-definitions.md)
- [Microsoft Purview データ損失防止についての説明](dlp-learn-about-dlp.md)
