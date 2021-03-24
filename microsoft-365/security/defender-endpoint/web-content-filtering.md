---
title: Web コンテンツ のフィルター処理
description: Microsoft Defender ATP の Web コンテンツ フィルターを使用して、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および調整します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、監視、レポート、カード、ドメイン リスト、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063723"
---
# <a name="web-content-filtering"></a>Web コンテンツ のフィルター処理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Web コンテンツ フィルターは現在パブリック プレビュー中です**<br>
> このプレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。 一部の機能はサポートされていないか、制限された機能を持っている可能性があります。
> 詳細については [、「Microsoft Defender for Endpoint プレビュー機能」を参照してください](preview.md)。

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web コンテンツ フィルターは [、Microsoft Defender](web-protection-overview.md) for Endpoint の Web 保護機能の一部です。 これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。 これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。

デバイス グループ全体のポリシーを構成して、特定のカテゴリをブロックします。 カテゴリをブロックすると、指定したデバイス グループ内のユーザーは、そのカテゴリに関連付けられた URL にアクセスできません。 ブロックされていないカテゴリの場合、URL は自動的に監査されます。 ユーザーは中断することなく URL にアクセスできます。また、アクセス統計を収集して、よりカスタム ポリシーの決定を作成できます。 表示しているページ上の要素がブロックされたリソースを呼び出している場合、ユーザーにブロック通知が表示されます。

Web コンテンツ フィルターは主要な Web ブラウザーで利用できます。ブロックは Windows Defender SmartScreen (Microsoft Edge) とネットワーク保護 (Chrome、Firefox、Brave、Opera) によって実行されます。 ブラウザーのサポートの詳細については、「前提条件」セクションを参照してください。

利点の概要:

- ユーザーが、オンプレミスまたは離れた場所を閲覧している場合でも、ブロックされたカテゴリの Web サイトにアクセスするのを防ぐ
- Microsoft Defender for Endpoint の役割ベースのアクセス制御設定で定義されているデバイス グループを使用して、ユーザーのグループにポリシー [を簡単に展開する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)
- 同じ中央の場所で Web レポートにアクセスし、実際のブロックと Web 使用状況を可視化

## <a name="user-experience"></a>ユーザー エクスペリエンス

サードパーティがサポートするブラウザーのブロック エクスペリエンスは、ネットワーク保護によって提供されます。これは、ブロックされた接続をユーザーに通知するシステム レベルのトーストを提供します。 

ブラウザー内での使い方が簡単な場合は、Microsoft Edge の使用を検討してください。

## <a name="prerequisites"></a>前提条件

この機能を試す前に、次の要件を満たしていることを確認してください。

- Windows 10 Enterprise E5 ライセンスまたは Microsoft 365 E3 + Microsoft 365 E5 セキュリティ アドオン。
- Microsoft Defender セキュリティ センター ポータルへのアクセス
- 最新の MoCAMP 更新プログラムを使用して Windows 10 Anniversary Update (バージョン 1607) 以降を実行しているデバイス。

SmartScreen Windows Defenderが有効ではない場合、ネットワーク保護はブロックを引き継ぐ。 デバイスで [ネットワーク保護を有効にする](enable-network-protection.md) 必要があります。 Chrome、Firefox、Brave、Opera は現在、この機能が有効になっているサードパーティのブラウザーです。

## <a name="data-handling"></a>データ処理

Microsoft Defender for Endpoint データ処理設定の一部として使用する選択した地域 [に従います](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)。 データは、その地域のデータ センターから離れる必要があります。 さらに、お客様のデータは、データ プロバイダーを含む第三者と共有されることはありません。

## <a name="turn-on-web-content-filtering"></a>Web コンテンツ フィルターを有効にする

左側のナビゲーション メニューで、[設定] を選択し、[全般 **>機能>選択します**。 Web コンテンツ フィルターのエントリが表示されるまで **下にスクロールします**。 トグルを [オン] と **[保存****] の基本設定に切り替えます**。

### <a name="configure-web-content-filtering-policies"></a>Web コンテンツ フィルター ポリシーの構成

Web コンテンツ フィルター ポリシーは、どのサイト カテゴリがどのデバイス グループでブロックされるのか指定します。 ポリシーを管理するには、[Web コンテンツ フィルターの **設定>ルール>に移動します**。

フィルターを使用して、特定のブロックされたカテゴリを含むポリシー、または特定のデバイス グループに適用されるポリシーを検索します。

### <a name="create-a-policy"></a>ポリシーの作成

新しいポリシーを追加するには、次の方法を使用します。

1. [設定 **] の** [Web コンテンツ フィルター] **ページで [ポリシーの** 追加] を **選択します**。
2. 名前を指定します。
3. ブロックするカテゴリを選択します。 展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。
4. ポリシー スコープを指定します。 ポリシーを適用する場所を指定するデバイス グループを選択します。 選択したデバイス グループ内のデバイスだけが、選択したカテゴリの Web サイトにアクセスできません。
5. 概要を確認し、ポリシーを保存します。 ポリシーの更新には、選択したデバイスに適用するために最大 2 時間かかる場合があります。

ヒント: デバイス グループでカテゴリを選択せずにポリシーを展開できます。 このアクションは、ブロック ポリシーを作成する前にユーザーの動作を理解するのに役立つ監査専用ポリシーを作成します。

>[!NOTE]
>ポリシーを削除したり、デバイス グループを同時に変更したりすると、ポリシーの展開が遅れる可能性があります。

>[!IMPORTANT]
>"未分類" カテゴリをブロックすると、予期しない結果が発生する可能性があります。  

### <a name="allow-specific-websites"></a>特定の Web サイトを許可する

Web コンテンツ フィルターでブロックされたカテゴリを上書きして、カスタム インジケーター ポリシーを作成して 1 つのサイトを許可できます。 カスタム インジケーター ポリシーは、Web コンテンツ フィルター ポリシーが問題のデバイス グループに適用されると、そのポリシーに取って代えられます。

1. [設定インジケーター URL/ドメインの追加アイテム] に移動して、Microsoft Defender セキュリティ センターでカスタム インジケーター  >    >  **を**  >  **作成する**
2. サイトのドメインを入力する
3. ポリシー アクションを [許可] に **設定します**。  

### <a name="reporting-inaccuracies"></a>不正確なレポート

誤って分類されたドメインが発生した場合は、[Web コンテンツ フィルター レポート] ページから不正確な情報を直接報告できます。 この機能は、新しい Microsoft 365 セキュリティ センター (security.microsoft.com) でのみ使用できます。

不正確な情報を報告するには、[Web コンテンツ フィルターの詳細>ドメイン> **レポート] >移動します**。 Web コンテンツ フィルター レポートの [ドメイン] タブに、各ドメインの横に省略記号が表示されます。 この省略記号にカーソルを合わせると、[ **不正確なレポート] を選択します**。

パネルが開き、優先度を選択し、再分類の推奨カテゴリなどの詳細を追加できます。 フォームが完成したら、[送信] を **選択します**。 チームは 1 営業日以内に要求を確認します。 ブロック解除を直ちに行う場合は、カスタム許可 [インジケーターを作成します](indicator-ip-domain.md)。

## <a name="web-content-filtering-cards-and-details"></a>Web コンテンツ フィルター カードと詳細

[ **レポートと web >]** を選択して、Web コンテンツ フィルターと Web 脅威保護に関する情報を含むカードを表示します。 次のカードは、Web コンテンツ フィルターに関する概要情報を提供します。

### <a name="web-activity-by-category"></a>カテゴリ別の Web アクティビティ

このカードには、アクセス試行回数の増加または減少が最も大きい親 Web コンテンツ カテゴリが一覧表示されます。 過去 30 日間、3 か月、または 6 か月の組織の Web アクティビティ パターンの大幅な変化を理解します。 詳細を表示するには、カテゴリ名を選択します。

この機能を使用した最初の 30 日間で、組織にはこの情報を表示するのに十分なデータが含めなかった可能性があります。

![カテゴリ カード別の Web アクティビティのイメージ](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a>Web コンテンツ フィルターの概要カード

このカードは、異なる親 Web コンテンツ カテゴリに対するブロックされたアクセス試行の分布を表示します。 色付きバーのいずれかを選択して、特定の親 Web カテゴリに関する詳細を表示します。

![Web コンテンツ フィルターの概要カードのイメージ](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a>Web アクティビティの概要カード

このカードには、すべての URL の Web コンテンツに対する要求の総数が表示されます。

![Web アクティビティの概要カードの画像](images/web-activity-summary.png)

### <a name="view-card-details"></a>カードの詳細を表示する

カード内のグラフ **からテーブル** 行または色付きバーを選択すると、各カードのレポートの詳細にアクセスできます。 各カードのレポートの詳細ページには、Web コンテンツ カテゴリ、Web サイト ドメイン、デバイス グループに関する広範な統計データが含まれています。

![Web 保護レポートの詳細の画像](images/web-protection-report-details.png)

- **Web カテゴリ**: 組織内でアクセス試行を行った Web コンテンツ カテゴリを一覧表示します。 特定のカテゴリを選択してサマリー フライアウトを開きます。

- **ドメイン**: 組織でアクセスまたはブロックされた Web ドメインを一覧表示します。 特定のドメインを選択して、そのドメインに関する詳細情報を表示します。

- **デバイス グループ**: 組織で Web アクティビティを生成したデバイス グループの一覧を表示します。

ページの左上にある時間範囲フィルターを使用して、期間を選択します。 情報をフィルター処理したり、列をカスタマイズしたりすることもできます。 行を選択して、選択したアイテムに関するさらに詳しい情報を含むフライアウト ウィンドウを開きます。

## <a name="errors-and-issues"></a>エラーと問題

### <a name="limitations-and-known-issues-in-this-preview"></a>このプレビューの制限事項と既知の問題

- デバイスの OS 構成が Server (cmd > Systeminfo > OS 構成) の場合にのみ、Microsoft Edge がサポートされます。 ネットワーク保護は、サポートされているサードパーティのブラウザー間のトラフィックをセキュリティ保護するサーバー デバイスの検査モードでのみサポートされます。

- 割り当てられていないデバイスでは、レポート内に正しくないデータが表示されます。 [デバイス グループのレポート>] ピボットに、空白の [デバイス グループ] フィールドを含む行が表示される場合があります。 このグループには、割り当てられていないデバイスが指定したグループに入る前に含まれる。 この行のレポートには、デバイスの正確な数やアクセス数が含まれているとは思えない。

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web 脅威保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威に対応する](web-protection-response.md)
