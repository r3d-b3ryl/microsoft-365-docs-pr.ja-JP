---
title: '[アラートの調査] Microsoft 365 Defender'
description: デバイス、ユーザー、メールボックス間で表示されるアラートを調査します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.technology: m365d
ms.openlocfilehash: 2dcc7e57182df3fe0a06bb1713b3a0786f35e144
ms.sourcegitcommit: cde34d38bdfb6335b980f1c48c6b218da6a64bf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2022
ms.locfileid: "62156138"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>[アラートの調査] Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントや不審なイベントが発生したかどうかを示します。 アラートは通常、より広範な攻撃の一部であり、インシデントに関する手がかりを提供します。

このMicrosoft 365 Defender関連するアラートは、インシデントを形成するために[まとめて集計されます](incidents-overview.md)。 インシデントは常に攻撃の広範なコンテキストを提供しますが、アラートの分析は、より深い分析が必要な場合に有用です。 

アラート **キューには、** 現在の一連のアラートが表示されます。 [インシデント] ポータルのクイック **起動時**&通知>通知キューに <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderされます</a>。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="ポータル内のアラート キューのMicrosoft 365 Defenderします。":::

Microsoft Defender for Endpoint、Microsoft Defender for endpoint、Microsoft Defender for microsoft Defender など、さまざまな Microsoft セキュリティ Office 365、Microsoft 365 Defenderここに表示されます。

既定では、ポータルのアラート キュー Microsoft 365 Defender過去 30 日間の新しいアラートと進行中のアラートが表示されます。 最新のアラートはリストの一番上に表示されます。最初に確認できます。 

既定のアラート キューから [フィルター] を選択 **すると、[** フィルター] ウィンドウが表示され、そこからアラートのサブセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="ポータル内のアラート キューのフィルター ウィンドウのMicrosoft 365 Defenderします。":::

次の条件に従ってアラートをフィルター処理できます。

- 重要度
- 状態
- サービス ソース
- 影響を受け取ったアセット
- 自動調査の状態

## <a name="required-roles-for-defender-for-office-365-alerts"></a>ユーザー通知の Defender に必要Office 365役割

Microsoft Defender にアクセスして警告を表示するには、次の役割Office 365があります。

- グローバル Azure Active Directory (Azure AD) の場合:

   - グローバル管理者

   - セキュリティ管理者

   - セキュリティ オペレーター

   - グローバル閲覧者

   - セキュリティ閲覧者

- Office 365 セキュリティ &コンプライアンス 役割グループ

   - コンプライアンス管理者

   - 組織管理 

- カスタム [ロール](custom-roles.md)

## <a name="analyze-an-alert"></a>アラートの分析

メインのアラート ページを表示するには、アラートの名前を選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="ポータル内のアラートの詳細ページMicrosoft 365 Defenderします。":::

[警告の管理] ウィンドウ **から [メインのアラート ページを開** く] **アクションを選択** することもできます。

アラート ページは、次のセクションで構成されます。 

- アラート ストーリー(このアラートに関連するイベントとアラートの連鎖を時系列順に示す)
- 概要の詳細

アラート ページ全体で、任意のエンティティの横にある省略記号 (**...**) を選択して、アラート ページを開く、またはアラートを別のインシデントにリンクするなどの使用可能なアクションを表示できます。

### <a name="alert-sources"></a>アラート ソース

Microsoft 365 Defenderは、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、Microsoft Defender for Cloud Apps のアプリ ガバナンス アドオンのようなソリューションから発生する場合があります。 警告の先頭に文字が付加されたアラートが表示されることがあります。 次の表は、アラートの先頭に付加された文字に基づくアラート ソースのマッピングを理解するのに役立つガイダンスを示しています。

> [!NOTE]
> - 付加された GUID は、統合アラート キュー、統合アラート ページ、統合調査、統合インシデントなどの統合エクスペリエンスにのみ固有です。
> - 先頭に付加された文字は、アラートの GUID を変更しない。 GUID に対する唯一の変更は、先頭に追加されたコンポーネントです。

| アラート ソース | 先頭文字 |
| :---|:--- |
| Microsoft Defender for Office 365 | `fa{GUID}` <br> 例: `fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Endpoint | `da` または `ed` カスタム検出アラートの場合 <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> 例: `aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> 例: `ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>影響を受けるアセットを分析する

[ **実行されたアクション** ] セクションには、このアラートの影響を受けるメールボックス、デバイス、ユーザーなど、影響を受けるアセットの一覧があります。 

[アクション センターで表示 **] を選択して**、ポータルの[アクション センター] の [履歴] タブMicrosoft 365 Defenderすることもできます。  

### <a name="trace-an-alerts-role-in-the-alert-story"></a>アラート ストーリー内のアラートの役割を追跡する

アラート ストーリーは、プロセス ツリー ビューでアラートに関連付けのすべてのアセットまたはエンティティを表示します。 タイトル内のアラートは、選択したアラートのページに最初に着陸した場合にフォーカスを置くアラートです。 アラート ストーリー内のアセットは展開可能でクリック可能です。 アラート ページのコンテキストでアクションを実行できるようにして、追加情報を提供し、応答を迅速化します。 

> [!NOTE]
> [アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。

### <a name="view-more-alert-information-on-the-details-page"></a>詳細ページでアラートの詳細情報を表示する

[詳細] ページには、選択したアラートの詳細と、そのアラートに関連する詳細とアクションが表示されます。 アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ページが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。

目的のエンティティを選択すると、詳細ページが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。

## <a name="manage-alerts"></a>アラートの管理

アラートを管理するには、その行のアラート キューでアラートを選択して、[警告の管理] **ウィンドウを表示** します。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="ポータル内のアラートの概要ウィンドウのMicrosoft 365 Defenderします。":::

[ **警告の管理]** ウィンドウでは、次の項目を表示または指定できます。

- アラートの状態 (新規、解決済み、進行中)。
- アラートが割り当てられているユーザー アカウント。
- アラートの分類 (設定されていない、True アラート、False Alert)。
- 真のアラートとして分類する場合は、[決定] フィールドのアラートの脅威の種類 **を指定** します。
- アラートに関するコメント。

> [!NOTE]
> タグを使用してアラートを管理する方法の 1 つ。 Microsoft Defender for microsoft Defender for Office 365段階的に展開中で、現在プレビュー中です。 <br>
> 現在、変更されたタグ名は、更新後に作成された *アラートにのみ* 適用されます。 変更前に生成されたアラートには、更新されたタグ名は反映されません。 

このウィンドウから、次の追加アクションを実行することもできます。 

- メインアラート ページを開く
- Microsoft 脅威の専門家に相談する
- 提出の表示
- 別のインシデントへのリンク
- タイムラインでアラートを表示する
- 抑制ルールの作成

次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="ポータル内のアラートに対するアクションMicrosoft 365 Defender例":::

追加のアクションの一覧は、アラートの種類によって異なります。

## <a name="resolve-an-alert"></a>アラートを解決する

アラートの分析が完了し、解決したら、[アラートの管理] ウィンドウに移動し、その状態を [解決済み] としてマークし、False アラートまたは **True** アラートとして分類します。 true アラートの場合は、[決定] フィールドにアラートの脅威の種類 **を指定** します。

アラートを分類し、その決定を指定すると、Microsoft 365 Defenderを調整して、より多くの真のアラートと少ない誤った通知を提供できます。

## <a name="use-power-automate-to-triage-alerts"></a>アラートPower Automateトリアージに使用する

最新のセキュリティ操作 (SecOps) チームは、効果的に機能するために自動化が必要です。 実際の脅威の検出と調査に集中するために、SecOps チームは Power Automate を使用してアラートの一覧をトリアージし、脅威ではない脅威を排除します。  

### <a name="criteria-for-resolving-alerts"></a>アラートを解決するための条件

- ユーザーがアウトオブオフィス メッセージを有効にしている

- ユーザーが高リスクとしてタグ付けされていない

両方が true の場合、SecOps はアラートを正当な移動としてマークし、解決します。 通知は、通知が解決Microsoft Teams後に通知に投稿されます。

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Connect Power Automate Microsoft Defender for Cloud Apps への移行

オートメーションを作成するには、Microsoft Defender for Cloud Apps に接続する前Power Automate API トークンが必要です。

1. **[設定] をクリック** し **、[セキュリティ拡張機能]** を選択し、[API **トークン**] タブの [トークンの追加 **] をクリック** します。

2. トークンの名前を指定し、[生成] を **クリックします**。 後で必要に応じてトークンを保存します。

### <a name="create-an-automated-flow"></a>自動フローの作成

詳細な手順については、ビデオを参照 [してください](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)。

このビデオでは、電源自動化を Defender for Cloud Apps に接続する方法も説明します。

## <a name="next-steps"></a>次の手順

インプロセス インシデントの必要に応じて、調査を続行 [します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
