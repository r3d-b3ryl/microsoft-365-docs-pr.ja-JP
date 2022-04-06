---
title: Web 保護
description: Microsoft Defender for Endpointの Web 保護と、組織を保護する方法について説明します
keywords: Web 保護, Web 脅威保護, Web 閲覧, セキュリティ, フィッシング, マルウェア, 悪用, Web サイト, ネットワーク保護, Edge, Internet Explorer, Chrome, Firefox, Web ブラウザー, 悪意のある Web サイト
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
ms.openlocfilehash: 4184948316e683a59b45b9397aaea74260e290ee
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664174"
---
# <a name="web-protection"></a>Web 保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)


## <a name="about-web-protection"></a>Web 保護について

Microsoft Defender for Endpointの Web 保護は、[Web 脅威保護](web-threat-protection.md)、[Web コンテンツ フィルタリング](web-content-filtering.md)、カスタム インジケーターで構成される機能[です](manage-indicators.md)。 Web 保護を使用すると、Web の脅威からデバイスを保護し、不要なコンテンツを規制するのに役立ちます。 Web 保護レポートは、Microsoft 365 Defender ポータルの **[レポート] > [Web 保護]** に移動して確認できます。

:::image type="content" source="images/web-protection.png" alt-text="Web 保護カード" lightbox="images/web-protection.png":::

### <a name="web-threat-protection"></a>Web の脅威に対する保護

Web 脅威保護を構成するカードは、 **時間の経過に伴う Web 脅威の検出** と **Web 脅威の概要です**。

Web 脅威の保護には、次のものが含まれます。

- 組織に影響を与える Web 脅威を包括的に可視化します。
- アラートと、これらの URL にアクセスするデバイスの包括的なプロファイルを通じて、Web 関連の脅威アクティビティに対する調査機能。
- 悪意のある Web サイトや不要な Web サイトに対する一般的なアクセス傾向を追跡するセキュリティ機能の完全なセット。

詳細については、「 [Web 脅威の保護](web-threat-protection.md)」を参照してください。

### <a name="custom-indicators"></a>カスタム インジケーター

カスタム インジケーターの検出は、組織の Web 脅威レポートでも、 **時間の経過と共に Web 脅威の検出** と **Web 脅威の概要** にまとめられます。

カスタム インジケーターには、次のものが含まれます。

- 脅威から組織を保護するために、侵害の IP および URL ベースのインジケーターを作成する機能。
- カスタム IP/URL プロファイルと、これらの URL にアクセスするデバイスに関連するアクティビティに関する調査機能。
- IP と URL の許可、ブロック、警告のポリシーを作成する機能。

詳細については、「[IP と URL/ドメインのインジケーターを作成する」を](indicator-ip-domain.md)参照してください。

### <a name="web-content-filtering"></a>Web コンテンツ フィルタリング

Web コンテンツ フィルターには、 **カテゴリ別の Web アクティビティ**、 **Web コンテンツ フィルターの概要**、 **Web アクティビティの概要** が含まれます。

Web コンテンツ フィルターには、次のものが含まれます。

- ユーザーは、オンプレミスでも離れた場所でも、ブロックされたカテゴリの Web サイトにアクセスできなくなります。
- [Microsoft Defender for Endpointロールベースのアクセス制御設定](/microsoft-365/security/defender-endpoint/rbac)で定義されているデバイス グループを使用して、さまざまなユーザー セットにさまざまなポリシーを簡単にデプロイできます。
- 同じ中央の場所にある Web レポートにアクセスでき、実際のブロックと Web の使用状況を把握できます。

詳細については、「 [Web コンテンツ のフィルター処理](web-content-filtering.md)」を参照してください。

## <a name="order-of-precedence"></a>優先順位

Web 保護は、次のコンポーネントで構成され、優先順位の順に一覧表示されます。 これらの各コンポーネントは、Microsoft Edgeの SmartScreen クライアントと、他のすべてのブラウザーとプロセスの Network Protection クライアントによって適用されます。

- カスタム インジケーター (IP/URL、Microsoft Defender for Cloud Apps ポリシー)
  - 許可
  - 警告
  - ブロック

- Web の脅威 (マルウェア、フィッシング)
  - SmartScreen Intel(Exchange Online Protection (EOP) を含む)
  - エスカレーション

- Web コンテンツ フィルター (WCF)

> [!NOTE]
> Microsoft Defender for Cloud Apps現在、ブロックされた URL に対してのみインジケーターが生成されます。

優先順位は、URL または IP が評価される操作の順序に関連します。 たとえば、Web コンテンツ フィルター ポリシーがある場合は、カスタム IP/URL インジケーターを使用して除外を作成できます。 侵害のカスタム インジケーター (IoC) は、WCF ブロックよりも優先順位が高くなります。

同様に、インジケーター間の競合中は、常にブロックよりも優先されます (ロジックのオーバーライド)。 つまり、許可インジケーターが存在するすべてのブロック インジケーターに勝ちます。

次の表は、Web 保護スタック内で競合が発生するいくつかの一般的な構成をまとめたものです。 また、上記の優先順位に基づいて、結果の決定も識別されます。

<br>

****

|カスタム インジケーター ポリシー|Web 脅威ポリシー|WCF ポリシー|Defender for Cloud アプリ ポリシー|結果|
|---|---|---|---|---|
|許可|ブロック|ブロック|ブロック|許可 (Web 保護のオーバーライド)|
|許可|許可|ブロック|ブロック|許可 (WCF 例外)|
|警告|ブロック|ブロック|ブロック|警告 (オーバーライド)|
|

内部 IP アドレスは、カスタム インジケーターではサポートされていません。 エンド ユーザーによってバイパスされた場合の警告ポリシーの場合、サイトは既定でそのユーザーに対して 24 時間ブロック解除されます。 この期間は管理者が変更でき、SmartScreen クラウド サービスによって渡されます。 警告をバイパスする機能は、web 脅威ブロック (マルウェア/フィッシング) の CSP を使用してMicrosoft Edgeで無効にすることもできます。 詳細については、「[SmartScreen 設定のMicrosoft Edge」を](/DeployEdge/microsoft-edge-policies#smartscreen-settings-policies)参照してください。

## <a name="protect-browsers"></a>ブラウザーを保護する

すべての Web 保護シナリオでは、SmartScreen と Network Protection を一緒に使用して、ファースト パーティとサード パーティの両方のブラウザーとプロセス間で保護を確保できます。 SmartScreen はMicrosoft Edgeに直接組み込まれていますが、Network Protection はサードパーティのブラウザーとプロセスでトラフィックを監視します。 次の図は、この概念を示しています。 複数のブラウザー/アプリカバレッジを提供するために連携する 2 つのクライアントのこの図は、Web Protection のすべての機能 (インジケーター、Web 脅威、コンテンツ フィルター) に対して正確です。

:::image type="content" source="../../media/web-protection-protect-browsers.png" alt-text="smartScreen と Network Protection の併用" lightbox="../../media/web-protection-protect-browsers.png":::

## <a name="troubleshoot-endpoint-blocks"></a>エンドポイント ブロックのトラブルシューティング

SmartScreen クラウドからの応答は標準化されています。 Fiddler などのツールを使用してクラウド サービスからの応答を調べることができます。これは、ブロックのソースを特定するのに役立ちます。

SmartScreen クラウド サービスが許可、ブロック、または警告応答で応答すると、応答カテゴリとサーバー コンテキストがクライアントに中継されます。 Microsoft Edgeでは、応答カテゴリは、表示する適切なブロック ページ (悪意のある、フィッシング、組織のポリシー) を決定するために使用されます。

次の表は、応答とその相関特徴を示しています。

<br>

****

|ResponseCategory|ブロックを担当する機能|
|---|---|
|CustomPolicy|WCF|
|CustomBlockList|カスタム インジケーター|
|CasbPolicy|Defender for Cloud Apps|
|悪意がある|Web の脅威|
|フィッシング|Web の脅威|
|||

## <a name="advanced-hunting-for-web-protection"></a>Web 保護のための高度なハンティング

高度な捜索のKustoクエリを使用すると、組織内の Web 保護ブロックを最大 30 日間集計できます。 これらのクエリでは、上記の情報を使用して、ブロックのさまざまなソースを区別し、ユーザー フレンドリな方法で集計します。 たとえば、次のクエリでは、Microsoft Edgeから発信されるすべての WCF ブロックが一覧表示されます。

```kusto
DeviceEvents
| where ActionType == "SmartScreenUrlWarning"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, Experience=tostring(ParsedFields.Experience)
| where Experience == "CustomBlockList"
```

同様に、次のクエリを使用して、Network Protection から発信されたすべての WCF ブロック (サードパーティのブラウザーの WCF ブロックなど) を一覧表示できます。 ActionType が更新され、'Experience' が 'ResponseCategory' に変更されていることに注意してください。

```kusto
DeviceEvents
| where ActionType == "ExploitGuardNetworkProtectionBlocked"
| extend ParsedFields=parse_json(AdditionalFields)
| project DeviceName, ActionType, Timestamp, RemoteUrl, InitiatingProcessFileName, ResponseCategory=tostring(ParsedFields.ResponseCategory)
| where ResponseCategory == "CustomPolicy"
```

他の機能 (カスタム インジケーターなど) に起因するブロックを一覧表示するには、上の表に各機能とそれぞれの応答カテゴリの概要を示します。 これらのクエリは、組織内の特定のマシンに関連するテレメトリを検索するように変更することもできます。 上記の各クエリに表示されている ActionType には、Web 保護機能によってブロックされた接続のみが表示され、すべてのネットワーク トラフィックが表示されないことに注意してください。

## <a name="user-experience"></a>ユーザー エクスペリエンス

ユーザーがマルウェア、フィッシング、またはその他の Web 脅威のリスクのある Web ページにアクセスした場合、Microsoft Edgeは、脅威に関連する情報と共に "このサイトは安全でないと報告されました" というブロック ページをトリガーします。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-malicious-block.png" alt-text="Microsoft Edgeによってブロックされたページ" lightbox="../../media/web-protection-malicious-block.png":::

WCF またはカスタム インジケーターによってブロックされた場合、このサイトが組織によってブロックされていることをユーザーに伝えるブロック ページがMicrosoft Edgeに表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-indicator-blockpage.png" alt-text="組織によってブロックされたページ" lightbox="../../media/web-protection-indicator-blockpage.png":::

いずれの場合も、サード パーティのブラウザーにはブロック ページは表示されません。ユーザーには"セキュリティで保護された接続に失敗しました" ページとトースト通知が表示されます。 ブロックを担当するポリシーに応じて、トースト通知に別のメッセージが表示されます。 たとえば、Web コンテンツ フィルターでは、"このコンテンツはブロックされています" というメッセージが表示されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="../../media/web-protection-np-block.png" alt-text="WCF によってブロックされたページ" lightbox="../../media/web-protection-np-block.png":::

## <a name="report-false-positives"></a>誤検知を報告する

SmartScreen によって危険と見なされたサイトの誤検知を報告するには、(上に示すように) Microsoft Edgeのブロック ページに表示されるリンクを使用します。

WCF の場合、ドメインのカテゴリに異議を申し合うことができます。 WCF レポートの **[ドメイン** ] タブに移動し、[ **レポートの不正確さ**] をクリックします。 ポップアップが開きます。 インシデントの優先度を設定し、推奨されるカテゴリなどの追加の詳細を指定します。 WCF を有効にする方法とカテゴリに異議を申し出る方法の詳細については、 [Web コンテンツのフィルター処理](web-content-filtering.md)に関するページを参照してください。

false positives/negatives を送信する方法の詳細については、「[Microsoft Defender for Endpointのアドレスの誤検知/否定](defender-endpoint-false-positives-negatives.md)」を参照してください。

## <a name="related-information"></a>関連情報

<br>

****

|トピック|説明|
|---|---|
|[Web の脅威に対する保護](web-threat-protection.md) | フィッシング サイト、マルウェア ベクトル、悪用サイト、信頼されていないサイトまたは低評価のサイト、ブロックしたサイトへのアクセスを停止します。|
|[Web コンテンツ フィルタリング](web-content-filtering.md) | コンテンツ カテゴリに基づいて、Web サイトへのアクセスを追跡および規制します。|
|
