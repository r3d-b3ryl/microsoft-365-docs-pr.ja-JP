---
title: Web コンテンツ フィルタリング
description: Microsoft Defender for Endpoint の Web コンテンツ フィルターを使用して、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、監視、レポート、カード、ドメイン リスト、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7395e7fb22c8ad090ab35868d385fa240700505c
ms.sourcegitcommit: b3c4816b55657b87ed4a5f6a4abe3d505392218e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2021
ms.locfileid: "53757359"
---
# <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> **Web コンテンツ フィルターは現在パブリック プレビュー中です**<br>
> このプレビュー バージョンはサービス レベル アグリーメントなしで提供されているため、実稼働ワークロードでの使用はお勧めしません。 一部の機能はサポートされないか、機能が制限される可能性があります。
> 詳細については、「[Microsoft Defender for Endpoint のプレビュー機能](preview.md)」をご覧ください。

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web コンテンツ フィルターは [、Microsoft Defender](web-protection-overview.md) for Endpoint の Web 保護機能の一部です。 これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。 これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。

デバイス グループ全体のポリシーを構成して、特定のカテゴリをブロックします。 カテゴリをブロックすると、指定したデバイス グループ内のユーザーは、そのカテゴリに関連付けられた URL にアクセスできません。 ブロックされていないカテゴリの場合、URL は自動的に監査されます。 ユーザーは中断することなく URL にアクセスできます。また、アクセス統計を収集して、よりカスタム ポリシーの決定を作成できます。 表示しているページ上の要素がブロックされたリソースを呼び出している場合、ユーザーにブロック通知が表示されます。

Web コンテンツ フィルターは主要な Web ブラウザーで利用できます。ブロックは Windows Defender SmartScreen (Microsoft Edge) とネットワーク保護 (Chrome、Firefox、Brave、および Opera) によって実行されます。 ブラウザーのサポートの詳細については、「前提条件」セクションを参照してください。

利点の概要:

- ユーザーが、オンプレミスまたは離れた場所を閲覧している場合でも、ブロックされたカテゴリの Web サイトにアクセスするのを防ぐ
- セキュリティ チームは、Microsoft Defender for Endpoint の役割ベースのアクセス制御設定で定義されているデバイス グループを使用して、ユーザーのグループにポリシーを簡単に [展開できます。](/microsoft-365/security/defender-endpoint/rbac)
- セキュリティ チームは、同じ中央の場所にある Web レポートにアクセスし、実際のブロックと Web 使用状況を可視化できます。

## <a name="prerequisites"></a>前提条件

この機能を試す前に、次の要件を満たしていることを確認してください。

- Windows 10 EnterpriseE5、Microsoft 365 E5、Microsoft 365 E5 Security、Microsoft 365 E3 + Microsoft 365 E5 Securityアドオン、または Microsoft Defender for Endpoint スタンドアロン ライセンス。 
- ポータルへのMicrosoft 365 Defender ( https://security.microsoft.com) .
- Anniversary update (Windows 10 1607) 以降で最新の MoCAMP 更新プログラムを使用して実行されているデバイス。
- Windows DefenderSmartScreen とネットワーク保護が有効です。

## <a name="user-experience"></a>ユーザー エクスペリエンス

サード パーティでサポートされているブラウザーのブロック エクスペリエンスは、ネットワーク保護によって提供されます。これは、ブロックされた接続をユーザーに通知するシステム レベルのトーストを提供します。 ユーザーフレンドリーでブラウザー内でのエクスペリエンスを向上するには、ユーザーエクスペリエンスの使用Microsoft Edge。

## <a name="data-handling"></a>データの処理

データは、Microsoft Defender for Endpoint データ処理設定の一部として選択された領域 [に格納されます](data-storage-privacy.md)。 データは、その地域のデータ センターから離れる必要があります。 さらに、お客様のデータは、データ プロバイダーを含む第三者と共有されることはありません。

## <a name="turn-on-web-content-filtering"></a>Web コンテンツ フィルターを有効にする

左側のナビゲーション メニューで、[エンドポイント **の** 全般設定  >  **機能**  >  **]**  >  **を選択します**。 Web コンテンツ フィルターのエントリが表示されるまで **下にスクロールします**。 トグルを [オン] と **[保存****] の基本設定に切り替えます**。

### <a name="configure-web-content-filtering-policies"></a>Web コンテンツ フィルター ポリシーの構成

Web コンテンツ フィルター ポリシーは、どのサイト カテゴリがどのデバイス グループでブロックされるのか指定します。 ポリシーを管理するには、[エンドポイント Web コンテンツ フィルター **設定** に移動します  >    >  ([ルール] の下)。

フィルターを使用して、特定のブロックされたカテゴリを含むポリシー、または特定のデバイス グループに適用されるポリシーを検索します。

### <a name="create-a-policy"></a>ポリシーの作成

新しいポリシーを追加するには、次の方法を使用します。

1. [Web **コンテンツ フィルター]** ページの **[ポリシーの追加] を選択****設定。**

2. 名前を指定します。

3. ブロックするカテゴリを選択します。 展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。

4. ポリシー スコープを指定します。 ポリシーを適用する場所を指定するデバイス グループを選択します。 選択したデバイス グループ内のデバイスだけが、選択したカテゴリの Web サイトにアクセスできません。

5. 概要を確認し、ポリシーを保存します。 ポリシーの更新には、選択したデバイスに適用するために最大 2 時間かかる場合があります。

> [!NOTE]
> - デバイス グループでカテゴリを選択せずにポリシーを展開できます。 このアクションは、ブロック ポリシーを作成する前にユーザーの動作を理解するのに役立つ監査専用ポリシーを作成します。
> - ポリシーを削除したり、デバイス グループを同時に変更したりすると、ポリシーの展開が遅れる可能性があります。
> - "未分類" カテゴリをブロックすると、予期しない結果が発生する可能性があります。  

### <a name="allow-specific-websites"></a>特定の Web サイトを許可する

Web コンテンツ フィルターでブロックされたカテゴリを上書きして、カスタム インジケーター ポリシーを作成して 1 つのサイトを許可できます。 カスタム インジケーター ポリシーは、Web コンテンツ フィルター ポリシーが問題のデバイス グループに適用されると、そのポリシーに取って代えられます。

1. [エンドポイントインジケーター URL/ドメイン追加アイテム] Microsoft 365 Defenderにアクセスして、設定ポータルにカスタム インジケーター  >    >    >  **を**  >  **作成します**。

2. サイトのドメインを入力します。

3. ポリシー アクションを [許可] に **設定します**。  

### <a name="dispute-categories"></a>紛争カテゴリ

誤って分類されたドメインが発生した場合は、ポータルから直接カテゴリに異議を申し立てできます。 

ドメインのカテゴリに異議を申し立てするには、[レポート Web 保護 Web コンテンツ フィルターの  >    >  **詳細ドメイン**]  >  **に移動します**。 Web コンテンツ フィルター レポートの [ドメイン] タブに、各ドメインの横に省略記号が表示されます。 この省略記号にカーソルを合わせると、[争議カテゴリ] **を選択します**。

パネルが開き、優先度を選択し、再分類の推奨カテゴリなどの詳細を追加できます。 フォームが完成したら、[送信] を **選択します**。 チームは 1 営業日以内に要求を確認します。 ブロック解除を直ちに行う場合は、カスタム許可 [インジケーターを作成します](indicator-ip-domain.md)。

### <a name="url-category-lookup"></a>URL カテゴリの参照

Web サイトのカテゴリを確認するには、ポータル ( ) で使用できる URL 検索Microsoft 365 Defender使用できます https://security.microsoft.com) 。 URL 検索結果では、[URL/ドメインの詳細] の下に Web コンテンツ フィルター **カテゴリが表示されます**。 管理者は、下の図に示すように、このページから直接ドメインのカテゴリに異議を申し立てすることもできます。 カテゴリの結果が表示されない場合、URL は現在、既存の Web コンテンツ フィルター カテゴリに割り当てられていない。

![Web コンテンツ フィルター カテゴリの参照結果の画像](../../media/web-content-filtering-category-lookup.png)

## <a name="web-content-filtering-cards-and-details"></a>Web コンテンツ フィルター カードと詳細

[**レポート**  >  **Web 保護] を** 選択して、Web コンテンツ フィルターと Web 脅威保護に関する情報を含むカードを表示します。 次のカードは、Web コンテンツ フィルターに関する概要情報を提供します。

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

- デバイスMicrosoft Edgeの OS 構成が Server **(cmd**  >  **Systeminfo**  >  **OS Configuration)** の場合にのみサポートされます。 ネットワーク保護は、サポートされているサード パーティ製ブラウザー間のトラフィックのセキュリティ保護を担当するサーバー デバイスの検査モードでのみサポートされます。

- 割り当てられていないデバイスでは、レポート内に正しくないデータが表示されます。 [レポートの **詳細]**[デバイス グループ] ピボットに、空白の [デバイス グループ] フィールド  >  を含む行が表示される場合があります。 このグループには、割り当てられていないデバイスが指定したグループに入る前に含まれる。 この行のレポートには、デバイスの正確な数やアクセス数が含まれている可能性があります。

- Web コンテンツ フィルター レポートは、現在、上位 5,000 レコードの表示に制限されています。 たとえば、ドメイン レポートには、該当する場合、特定のフィルター クエリの上位 5000 ドメインの最大数だけが表示されます。 



- [Web 保護の概要](web-protection-overview.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威への対応](web-protection-response.md)
- [ネットワーク保護の要件](web-content-filtering.md)

