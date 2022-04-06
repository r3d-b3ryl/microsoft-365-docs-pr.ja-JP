---
title: Microsoft 365 Defender でアラートを調査する
description: デバイス、ユーザー、メールボックス間で表示されるアラートを調査します。
keywords: インシデント、アラート、調査、調査、分析、応答、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、ID、メールボックス、電子メール、365、microsoft、m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: c09a3880a9f117d0ce5ce6e5edf3736192fc9c95
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499861"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defender でアラートを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

>[!Note]
>この記事では、セキュリティ アラートについて説明Microsoft 365 Defender。 ただし、アクティビティ通知を使用して、ユーザーがユーザーが特定のアクティビティを実行するときに、自分または他の管理者に電子メール通知を送信Microsoft 365。 詳細については、「Create [activity alerts - Microsoft 365 コンプライアンス |Microsoft Docs](../../compliance/create-activity-alerts.md)。

アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントや不審なイベントが発生したかどうかを示します。 アラートは通常、より広範な攻撃の一部であり、インシデントに関する手がかりを提供します。

このMicrosoft 365 Defender関連するアラートは、インシデントを形成するために[まとめて集計されます](incidents-overview.md)。 インシデントは常に攻撃の広範なコンテキストを提供しますが、アラートの分析は、より深い分析が必要な場合に有用です。

アラート **キューには、** 現在の一連のアラートが表示されます。 [インシデント] からアラート キューにアクセスし **&>** ポータルのクイック 起動時に通知をMicrosoft 365 Defender [します](https://go.microsoft.com/fwlink/p/?linkid=2077139)。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="[アラート] セクション (Microsoft 365 Defender ポータル)" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png":::

Microsoft Defender for Endpoint、Microsoft Defender for endpoint、Microsoft Defender for microsoft Defender など、さまざまな Microsoft セキュリティ ソリューションOffice 365、Microsoft 365 Defender表示されます。

既定では、Microsoft 365 Defenderポータルのアラート キューには、過去 30 日間の新しいアラートと進行中のアラートが表示されます。 最新のアラートはリストの一番上に表示されます。最初に確認できます。 

既定のアラート キューから [フィルター] を **選択すると、[** フィルター] ウィンドウが表示され、そこからアラートのサブセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="ポータルの [フィルター] Microsoft 365 Defenderします。" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png":::

次の条件に従ってアラートをフィルター処理できます。

- 重要度
- 状態
- サービス ソース
- エンティティ (影響を受け取ったアセット)
- 自動調査の状態

## <a name="required-roles-for-defender-for-office-365-alerts"></a>ユーザー通知に対する Defender の必須Office 365役割

Microsoft Defender にアクセスするには、次の役割を持つ必要があります。アラートOffice 365があります。

- グローバル Azure Active Directory (Azure AD) の場合:

   - グローバル管理者

   - セキュリティ管理者

   - セキュリティ オペレーター

   - グローバル閲覧者

   - セキュリティ閲覧者

- Office 365 セキュリティ &コンプライアンス役割グループ

   - コンプライアンス管理者

   - 組織管理 

- カスタム [ロール](custom-roles.md)

## <a name="analyze-an-alert"></a>アラートの分析

メインのアラート ページを表示するには、アラートの名前を選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="ポータル内のアラートのMicrosoft 365 Defender" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png":::

[警告の管理] ウィンドウ **から [メインのアラート ページを開** く] **アクションを選択** することもできます。

アラート ページは、次のセクションで構成されます。 

- アラート ストーリー(このアラートに関連するイベントとアラートの連鎖を時系列順に示す)
- 概要の詳細

アラート ページ全体で、任意のエンティティの横にある省略記号 (**...)** を選択すると、アラートを別のインシデントにリンクするなどの使用可能なアクションを確認できます。 使用可能なアクションの一覧は、アラートの種類によって異なります。

### <a name="alert-sources"></a>アラート ソース

Microsoft 365 Defenderは、Microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、Microsoft Defender for Cloud Apps のアプリ ガバナンス アドオンのようなソリューションから発生する場合があります。 警告の先頭に文字が付加されたアラートが表示されることがあります。 次の表は、アラートの先頭に付加された文字に基づくアラート ソースのマッピングを理解するのに役立つガイダンスを示しています。

> [!NOTE]
> - 付加された GUID は、統合アラート キュー、統合アラート ページ、統合調査、統合インシデントなどの統合エクスペリエンスにのみ固有です。
> - 先頭に付加された文字は、アラートの GUID を変更しない。 GUID に対する唯一の変更は、先頭に追加されたコンポーネントです。

| アラート ソース | 先頭文字 |
| :---|:--- |
| Microsoft Defender for Office 365 | `fa{GUID}` <br> 例: `fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Endpoint | `da` またはカスタム `ed` 検出アラートの場合 <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> 例: `aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> 例: `ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>影響を受けるアセットを分析する

[ **実行されたアクション** ] セクションには、このアラートの影響を受けるメールボックス、デバイス、ユーザーなど、影響を受けるアセットの一覧があります。 

[アクション センターで **表示] を選択して**、ポータルの [アクション センター] の [履歴] タブMicrosoft 365 Defenderすることもできます。 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>アラート ストーリー内のアラートの役割を追跡する

アラート ストーリーは、プロセス ツリー ビューでアラートに関連付けのすべてのアセットまたはエンティティを表示します。 タイトル内のアラートは、選択したアラートのページに最初に着陸した場合にフォーカスを置くアラートです。 アラート ストーリー内のアセットは展開可能でクリック可能です。 アラート ページのコンテキストでアクションを実行できるようにして、追加情報を提供し、応答を迅速化します。 

> [!NOTE]
> [アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。

### <a name="view-more-alert-information-on-the-details-page"></a>詳細ページでアラートの詳細情報を表示する

[詳細] ページには、選択したアラートの詳細と、そのアラートに関連する詳細とアクションが表示されます。 アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ページが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。

目的のエンティティを選択すると、詳細ページが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。

## <a name="manage-alerts"></a>アラートの管理

アラートを管理するには、アラート ページ **の** [概要の詳細] セクションで [アラートの管理] を選択します。 1 つのアラートの場合は、[警告の管理] ウィンドウの **例を次に示** します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="ポータルの [アラートの管理Microsoft 365 Defender]" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png":::

[ **警告の管理]** ウィンドウでは、次の項目を表示または指定できます。

- アラートの状態 (新規、解決済み、進行中)。
- アラートが割り当てられているユーザー アカウント。
- アラートの分類:

   - **[設定しない** ] (既定)。

   - **脅威の種類** に対して正の値を指定します。 実際の脅威を正確に示すアラートには、この分類を使用します。 脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。

   - **アクティビティの種類を含む、予想** される情報アクティビティ。 このカテゴリのオプションを使用して、セキュリティ テスト、赤いチーム アクティビティ、信頼できるアプリとユーザーからの予期される異常な動作に関するアラートを分類します。

   - **悪意のある** アクティビティがない場合でも作成されたアラートの種類に対して誤検知。 アラートを誤検知として分類するとMicrosoft 365 Defender品質が向上します。

- アラートに関するコメント。

> [!NOTE]
> タグを使用してアラートを管理する方法の 1 つ。 Microsoft Defender for microsoft Defender for Office 365段階的に展開中で、現在プレビュー中です。 <br>
> 現在、変更されたタグ名は、更新後に作成された *アラートにのみ* 適用されます。 変更前に生成されたアラートには、更新されたタグ名は反映されません。 

特定のアラート *に似た* 一連のアラートを管理するには、アラート ページの [概要の詳細] セクションの **[INSIGHT**] ボックスで [類似のアラートを表示する] を選択します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="ポータルでアラートをMicrosoft 365 Defenderする":::

[アラート **の管理]** ウィンドウで、関連するアラートを同時に分類できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="Microsoft 365 Defender ポータルでの関連Microsoft 365 Defender管理":::

同様のアラートが過去に既に分類されている場合は、他の通知がどのように解決されたのかMicrosoft 365 Defender推奨事項を使用して時間を節約できます。 [概要の詳細] セクションで、[推奨事項] **を選択します**。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="アラートの推奨事項の選択例":::

[ **推奨事項] タブ** には、調査、修復、および防止のための次の手順のアクションとアドバイスが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="アラートの推奨事項の例":::

## <a name="resolve-an-alert"></a>アラートを解決する

アラートの分析が完了したら、アラートまたは類似のアラートの [管理] アラート ウィンドウに移動し、状態を [解決済み] としてマークし、脅威の種類、アクティビティの種類が予想される情報アクティビティ、または False 陽性として分類します。 

アラートの分類は、Microsoft 365 Defender品質を向上させるのに役立ちます。

## <a name="use-power-automate-to-triage-alerts"></a>アラートPower Automateトリアージに使用する

最新のセキュリティ操作 (SecOps) チームは、効果的に機能するために自動化が必要です。 実際の脅威の検出と調査に集中するために、SecOps チームは Power Automate を使用してアラートの一覧をトリアージし、脅威ではない脅威を排除します。  

### <a name="criteria-for-resolving-alerts"></a>アラートを解決するための条件

- ユーザーがアウトオブオフィス メッセージを有効にしている

- ユーザーが高リスクとしてタグ付けされていない

両方が true の場合、SecOps はアラートを正当な移動としてマークし、解決します。 通知は、通知が解決Microsoft Teams後に通知に投稿されます。

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Connect Power Automate Microsoft Defender for Cloud Apps への移行

オートメーションを作成するには、Microsoft Defender for Cloud Apps に接続する前Power Automate API トークンが必要です。

1. [**設定**] をクリックし、[**セキュリティ拡張機能]** を選択し、[API **トークン**] タブの [トークンの追加 **] をクリック** します。

2. トークンの名前を指定し、[生成] を **クリックします**。 後で必要に応じてトークンを保存します。

### <a name="create-an-automated-flow"></a>自動フローの作成

詳細な手順については、ビデオを参照 [してください](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)。

このビデオでは、電源自動化を Defender for Cloud Apps に接続する方法も説明します。

## <a name="next-steps"></a>次の手順

インプロセス インシデントの場合は、必要に応じて調査を続行 [します](investigate-incidents.md)。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
