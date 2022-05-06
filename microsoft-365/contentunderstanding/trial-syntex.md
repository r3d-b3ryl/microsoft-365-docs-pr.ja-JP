---
title: Microsoft SharePoint Syntexの試用版を実行する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- Adopt
- admindeeplinkMAC
search.appverid: ''
ms.localizationpriority: medium
description: 組織内のSharePoint Syntexの試用版パイロット プログラムを計画、サインアップ、実行する方法について説明します。
ms.openlocfilehash: fc4221b0022aca8a0564c78e64d94028f6483104
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507101"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntexの試用版を実行する

この記事では、組織内にSharePoint Syntexを展開するための試用版パイロット プログラムを設定して実行する方法について説明します。 また、試用版のベスト プラクティスもお勧めします。

## <a name="sign-up-for-a-trial"></a>試用版にサインアップする

SharePoint Syntexの試用版では、300 人のユーザーに 30 日間アクセスできます。

> [!NOTE]
> 最大 300 人のユーザーが試用版に含まれ、100 万の AI Builder クレジットが自動的に追加されます。 試用版を成功させるには、300 人のユーザーを含める必要はありません。

試用版は、次のいずれかのソースから入手できます。

- [SharePoint Syntex製品ページ](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- [Microsoft 365 管理センター](https://admin.microsoft.com)
    1. [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。
    2. <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**BillingPurchase**</a> >  Services に移動します。
    3. **[アドオン]** セクションまで下にスクロールします。
    4. SharePoint Syntex タイルで、[詳細] を選択 **します**。
    5. [ **無料試用版の開始]** を選択します。
    6. 試用版を確認するには、残りのウィザードの手順に従います。

試用版をアクティブ化するには、Microsoft 365グローバル管理者または課金管理者である必要があります。

### <a name="who-should-be-involved-in-a-trial"></a>Whoは試用版に関与する必要があります

|役割|アクティビティ|
|---|---|
|グローバル管理者または課金管理者Microsoft 365|試用版をアクティブ化し、ライセンスを割り当てる|
|Microsoft 365 グローバル管理者または SharePoint 管理者|SharePoint Syntexを構成し、コンテンツ センターを作成する|
|ビジネス ユーザー|モデルの構築とテスト|

### <a name="before-you-activate-a-trial"></a>試用版をアクティブ化する前に

SharePoint Syntex試用版を正常に計画するには、次の要因を考慮してください。

- 最も意味のあるテストは、"現実世界" のシナリオとデータで完了します。
- SharePoint Syntex試用版は、テナントごとに 1 回だけアクティブ化できます。

テスト テナントまたはデモ テナントは、"ドライ ラン" として使用して、アクティブ化の手順と管理制御を実行できます。 ただし、運用テナントでのモデル構築を評価することをお勧めします。

運用テナントでの試用版の価値を最大化するには、計画とビジネスエンゲージメントが不可欠です。 SharePoint Syntexによって対処される可能性がある 3 から 6 のユース ケースを特定するために、1 つ以上のビジネス領域に関与する必要があります。 次のユース ケースが必要です。

- フォーム処理またはドキュメント理解モデルによって解決できるシナリオを含めます。
- 抽出されたメタデータの目的を明確に理解する。たとえば、Power Automateを使用して書式設定や自動化を表示します。 SharePoint Syntexはドキュメントの分類とメタデータの抽出に焦点を当てていますが、定量化する価値はこのメタデータで可能になります。
- 定義された一連のデータに基づく。たとえば、特定のSharePointサイトやライブラリなどです。 SharePoint Syntexの一般的な誤解は、汎用モデルをすべての組織のコンテンツに適用できるということです。 より正確なビューは、ターゲットとなる場所で特定のビジネス上の問題を解決するためにモデルが構築されていることです。

これらのユース ケースはすべて、SharePoint Syntexに適していない可能性があります。 品質評価版の目標は、SharePoint Syntexがすべてのシナリオに適合することを証明することではありません。 代わりに、試用版は、製品の価値をよりよく理解するのに役立ちます。

計画されているユース ケースごとに、関連するコンテンツまたはプロセスの主題の専門家であるユーザーを特定します。 SharePoint Syntex モデルの作成は、IT プロフェッショナルや開発者リソースではなく、コンテンツのドメインエキスパートに焦点を当てています。

## <a name="activate-a-trial"></a>試用版をアクティブ化する

試用版を開始するときは、次の操作を行う必要があります。

- 関連するユーザーにライセンスを割り当てます。
- [SharePoint Syntexの追加のセットアップを実行します](set-up-content-understanding.md)。
  - [追加のコンテンツ センターを作成](create-a-content-center.md)することもできます。

試用版がアクティブ化されたら、モデルとプロセス ファイルを作成できます。 [モデル作成のガイダンスを](create-a-content-center.md)参照してください。

## <a name="during-a-trial"></a>試用版中

試用期間は限られているため、最初は、SharePoint Syntex モデルでドキュメントを分類し、定義されたユース ケースのメタデータを抽出できるかどうかに重点を置くのが最善です。 試用期間が終了したら、メタデータを悪用する方法を評価できます。

## <a name="after-a-trial"></a>試用版の後

試用版の結果に基づいて、SharePoint Syntexの運用使用に進むかどうかを決定できます。

### <a name="proceed-to-production-use"></a>運用環境の使用に進む

サービスの継続性を確保するには、必要な数のライセンスを購入し、それらのライセンスをユーザーに割り当てる必要があります。 試用期間の終了時に完全なライセンスを持っていない試用版ユーザーは、SharePoint Syntexを完全に利用することはできません。

フォーム処理の予想される使用方法を見積もり、AI Builder クレジットの予想量を計画する必要がある場合があります。 ヘルプについては、「 [適切な AI Builder の容量を見積も](https://powerapps.microsoft.com/ai-builder-calculator/)る」を参照してください。

### <a name="dont-proceed-to-production-use"></a>運用環境での使用に進まない

試用版に従ってライセンスを購入しない場合:

- 新しいモデルを作成することはできません。
- モデルを実行していたライブラリでは、ファイルの分類やモデルの抽出が自動的に行われなくなりました。
- 以前に分類されたファイルや抽出されたメタデータは影響を受けることはありません。
- コンテンツ センターとドキュメント理解モデルは自動的に削除されません。 今後ライセンスを購入する場合は、引き続き使用できます。
- フォーム処理モデルは、既定の Power Platform 環境の Dataverse (以前は Common Data Service [CDS]) インスタンスに格納されます。 これらは、将来のSharePoint Syntex向けのライセンス、または Power Platform の AI Builder 機能で使用できます。

## <a name="see-also"></a>関連項目

[Microsoft SharePoint Syntex導入: 概要](adoption-getstarted.md)
