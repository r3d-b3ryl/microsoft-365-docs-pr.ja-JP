---
title: Web 保護
description: Microsoft Defender for Endpoint の Web 保護と、組織を保護する方法について説明します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー、悪意のある Web サイト
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7883ef4c7bc06c08e199af871902b26d8e46ac5e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476579"
---
# <a name="web-protection"></a>Web 保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)


## <a name="about-web-protection"></a>Web 保護について

Microsoft Defender for Endpoint の Web 保護は、 [Web](web-threat-protection.md) 脅威保護、 [Web](web-content-filtering.md) コンテンツ フィルター、およびカスタム インジケーターで構成される [機能です](manage-indicators.md)。 Web 保護を使用すると、Web の脅威からデバイスを保護し、望ましくないコンテンツを規制できます。 Web 保護のレポートは、[Web 保護のレポートMicrosoft 365 Defender]にアクセスして、>**できます**。

:::image type="content" source="images/web-protection.png" alt-text="Web 保護カード" lightbox="images/web-protection.png":::

### <a name="web-threat-protection"></a>Web の脅威に対する保護

Web 脅威保護を構成するカードは、 **時間** の過ぎた Web 脅威検出と **Web 脅威の概要です**。

Web 脅威保護には、次の機能が含まれます。

- 組織に影響を与える Web の脅威を包括的に可視化します。
- アラートと URL とこれらの URL にアクセスするデバイスの包括的なプロファイルを通じて、Web 関連の脅威アクティビティを調査する機能。
- 悪意のある Web サイトや望ましくない Web サイトへの一般的なアクセス傾向を追跡する一連のセキュリティ機能。

詳細については、「Web 脅威保護 [」を参照してください](web-threat-protection.md)。

### <a name="custom-indicators"></a>カスタム インジケーター

カスタム インジケーターの検出は、組織の Web 脅威レポートで、Web 脅威の検出と **Web** 脅威の概要の下に **まとめも行います**。

カスタム インジケーターには、次の情報が含まれます。

- IP および URL ベースの侵害の指標を作成して、組織を脅威から保護する機能。
- カスタム IP/URL プロファイルとこれらの URL にアクセスするデバイスに関連するアクティビティに関する調査機能。
- AP と URL の許可、ブロック、および警告ポリシーを作成する機能。

詳細については、「CREATE [indicators for IPs and URL/domains」を参照してください。](indicator-ip-domain.md)

### <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

Web コンテンツ フィルターには、 **カテゴリ別の Web アクティビティ**、 **Web コンテンツ** フィルターの概要、 **および Web アクティビティの概要が含まれます**。

Web コンテンツ フィルターには、次の機能が含まれます。

- ユーザーは、オンプレミスまたは離れた場所を参照している場合でも、ブロックされたカテゴリの Web サイトにアクセスする権限を持たれています。
- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/rbac) の役割ベースのアクセス制御設定で定義されているデバイス グループを使用して、さまざまなポリシーをさまざまなユーザー セットに簡単に展開できます。
- 同じ中央の場所で Web レポートにアクセスし、実際のブロックと Web 使用状況を可視化できます。

詳細については、「Web コンテンツ フィルター [」を参照してください](web-content-filtering.md)。

## <a name="order-of-precedence"></a>優先順位

Web 保護は、優先順位の順にリストされた次のコンポーネントで構成されます。 これらの各コンポーネントは、SmartScreen クライアントによって適用Microsoft Edge他のすべてのブラウザーとプロセスのネットワーク保護クライアントによって適用されます。

- カスタム インジケーター (IP/URL、Microsoft Defender for Cloud Apps ポリシー)
  - 許可
  - 警告
  - ブロック

- Web の脅威 (マルウェア、フィッシング)
  - SmartScreen Intel (EOP Exchange Online Protection含む)
  - エスカレーション

- Web コンテンツ フィルター (WCF)

> [!NOTE]
> Microsoft Defender for Cloud Apps は現在、ブロックされた URL についてのみインジケーターを生成します。

優先順位は、URL または IP が評価される操作の順序に関連します。 たとえば、Web コンテンツ フィルター ポリシーがある場合は、カスタム IP/URL インジケーターを使用して除外を作成できます。 カスタム 侵害のインジケーター (IoC) は、WCF ブロックよりも優先順位が高くなります。

同様に、インジケーター間の競合時には、常にブロック (オーバーライド ロジック) よりも優先されます。 つまり、許可インジケーターは、存在するブロック インジケーターに勝ちます。

次の表は、Web 保護スタック内で競合が発生する一般的な構成の概要を示しています。 また、上記の優先順位に基づいて、結果の判定を識別します。

<br>

****

|カスタム インジケーター ポリシー|Web 脅威ポリシー|WCF ポリシー|Defender for Cloud Apps ポリシー|結果|
|---|---|---|---|---|
|許可|ブロック|ブロック|ブロック|許可 (Web 保護の上書き)|
|許可|許可|ブロック|ブロック|許可 (WCF 例外)|
|警告|ブロック|ブロック|ブロック|警告 (オーバーライド)|
|

内部 IP アドレスは、カスタム インジケーターではサポートされていません。 エンド ユーザーがバイパスした場合の警告ポリシーの場合、既定では、そのユーザーのサイトのブロックが 24 時間解除されます。 この時間枠は管理者によって変更され、SmartScreen クラウド サービスによって受け渡されます。 また、CSP を使用して Web 脅威ブロック (マルウェア/フィッシング) を使用Microsoft Edge警告をバイパスする機能を無効にできます。 詳細については、「[SmartScreen Microsoft Edge」を参照設定](/DeployEdge/microsoft-edge-policies#smartscreen-settings-policies)。

## <a name="protect-browsers"></a>ブラウザーを保護する

すべての Web 保護シナリオでは、SmartScreen とネットワーク保護を組み合わせて使用して、第 1 および第三者のブラウザーとプロセスの両方で保護を確保できます。 SmartScreen は、サードパーティのブラウザー Microsoft Edgeプロセスでトラフィックを監視する一方で、ネットワーク保護は、ユーザーのネットワークに直接組み込み可能です。 次の図は、この概念を示しています。 複数のブラウザー/アプリ範囲を提供するために一緒に作業している 2 つのクライアントのこの図は、Web 保護のすべての機能 (インジケーター、Web 脅威、コンテンツ フィルター) に対して正確です。

:::image type="content" source="../../media/web-protection-protect-browsers.png" alt-text="smartScreen とネットワーク保護を一緒に使用する" lightbox="../../media/web-protection-protect-browsers.png":::

## <a name="troubleshoot-endpoint-blocks"></a>エンドポイント ブロックのトラブルシューティング

SmartScreen クラウドからの応答は標準化されています。 Fiddler のようなツールを使用して、クラウド サービスからの応答を調べ、ブロックのソースを特定するのに役立ちます。

SmartScreen クラウド サービスが応答を許可、ブロック、または警告すると、応答カテゴリとサーバー コンテキストがクライアントに中継されます。 このMicrosoft Edge、応答カテゴリは、表示する適切なブロック ページ (悪意のある、フィッシング、組織のポリシー) を決定するために使用されます。

次の表は、応答とその相関機能を示しています。

<br>

****

|ResponseCategory|ブロックを担当する機能|
|---|---|
|CustomPolicy|WCF|
|CustomBlockList|カスタム インジケーター|
|CasbPolicy|Defender for Cloud Apps|
|悪意がある|Web の脅威|
|フィッシング詐欺|Web の脅威|
|||

## <a name="advanced-hunting-for-web-protection"></a>Web 保護のための高度な検索

高度な検索の Kusto クエリを使用すると、組織内の Web 保護ブロックを最大 30 日間要約できます。 これらのクエリでは、上記の情報を使用して、ブロックのさまざまなソースを区別し、ユーザーフレンドリーな方法で要約します。 たとえば、次のクエリは、次のクエリから発生する WCF ブロックMicrosoft Edge。

```kusto
DeviceEvents
| where ActionType == "SmartScreenUrlWarning"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, Experience=tostring(ParsedFields.Experience)
| where Experience == "CustomBlockList"
```

同様に、以下のクエリを使用して、ネットワーク保護から発信される WCF ブロック (サードパーティ ブラウザーの WCF ブロックなど) を一覧表示できます。 ActionType が更新され、'Experience' が 'ResponseCategory' に変更された点に注意してください。

```kusto
DeviceEvents
| where ActionType == "ExploitGuardNetworkProtectionBlocked"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, ResponseCategory=tostring(ParsedFields.ResponseCategory)
| where ResponseCategory == "CustomPolicy"
```

他の機能 (カスタム インジケーターなど) が原因のブロックを一覧表示するには、上の表を参照して、各機能とそれぞれの応答カテゴリの説明を参照してください。 これらのクエリは、組織内の特定のコンピューターに関連するテレメトリを検索するために変更される場合もあります。 上記の各クエリに示す ActionType には、Web Protection 機能によってブロックされた接続だけが表示され、すべてのネットワーク トラフィックが表示されるという点に注意してください。

## <a name="user-experience"></a>ユーザー エクスペリエンス

ユーザーがマルウェア、フィッシング、その他の Web 脅威のリスクを引き起こす Web ページにアクセスした場合、Microsoft Edge は、脅威に関連する情報と共に「このサイトが安全でないと報告されている」というブロック ページをトリガーします。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-malicious-block.png" alt-text="ページがブロックMicrosoft Edge" lightbox="../../media/web-protection-malicious-block.png":::

WCF またはカスタム インジケーターによってブロックされている場合、このサイトが組織によってブロックMicrosoft Edgeにブロック ページが表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-indicator-blockpage.png" alt-text="組織によってブロックされたページ" lightbox="../../media/web-protection-indicator-blockpage.png":::

いずれにしても、サード パーティのブラウザーにブロック ページは表示されません。ユーザーにはトースト通知と共に 「Secure Connection Failed」ページが表示されます。 ブロックを担当するポリシーに応じて、ユーザーはトースト通知に別のメッセージを表示します。 たとえば、Web コンテンツ フィルターでは、「このコンテンツはブロックされています」というメッセージが表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-np-block.png" alt-text="WCF によってブロックされるページ" lightbox="../../media/web-protection-np-block.png":::

## <a name="report-false-positives"></a>誤検知を報告する

SmartScreen によって危険と判断されたサイトに対して誤検知を報告するには、上記のように、Microsoft Edge のブロック ページに表示されるリンクを使用します。

WCF では、ドメインのカテゴリに異議を申し立てできます。 WCF レポートの **[ドメイン]** タブに移動し、[不正確なレポート] **をクリックします**。 フライアウトが開きます。 インシデントの優先度を設定し、推奨されるカテゴリなどの追加の詳細を提供します。 WCF を有効にする方法とカテゴリに異議を申し立てする方法の詳細については、「Web コンテンツ フィルター [」を参照してください](web-content-filtering.md)。

誤検知/負を送信する方法の詳細については、「 [Address false positives/negatives in Microsoft Defender for Endpoint」を参照してください](defender-endpoint-false-positives-negatives.md)。

## <a name="related-information"></a>関連情報

<br>

****

|トピック|説明|
|---|---|
|[Web の脅威に対する保護](web-threat-protection.md) | フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、ブロックしたサイトへのアクセスを停止します。|
|[Web コンテンツ フィルタリング](web-content-filtering.md) | コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および調整します。|
|
