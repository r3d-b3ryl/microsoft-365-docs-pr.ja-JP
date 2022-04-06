---
title: Microsoft 365 Defender でアラートを調査する
description: デバイス、ユーザー、メールボックス間で見られるアラートを調査します。
keywords: インシデント, アラート, 調査, 分析, 応答, 相関関係, 攻撃, マシン, デバイス, ユーザー, ID, ID, メールボックス, 電子メール, 365, Microsoft, m365
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
ms.openlocfilehash: 20ae5bd77b9a4a962093db1e3d92d8f765a9a9a3
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664702"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defender でアラートを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

>[!Note]
>この記事では、Microsoft 365 Defenderのセキュリティ アラートについて説明します。 ただし、アクティビティ アラートを使用すると、ユーザーがMicrosoft 365で特定のアクティビティを実行したときに、自分や他の管理者に電子メール通知を送信できます。 詳細については、「[アクティビティ アラートの作成 - コンプライアンス |Microsoft 365」を参照してください。Microsoft Docs](../../compliance/create-activity-alerts.md)。

アラートは、すべてのインシデントの基礎であり、環境内で悪意のあるイベントまたは疑わしいイベントが発生したことを示します。 通常、アラートは広範な攻撃の一部であり、インシデントに関する手がかりを提供します。

Microsoft 365 Defenderでは、関連するアラートが集計されて[インシデントが形成されます](incidents-overview.md)。 インシデントは常に攻撃の広範なコンテキストを提供しますが、より深い分析が必要な場合、アラートを分析することは有益な場合があります。

**アラート キュー** には、現在の一連のアラートが表示されます。 Microsoft 365 Defender ポータルのクイック起動時に、**インシデント&アラート>アラートからアラート** キューにアクセス [します](https://go.microsoft.com/fwlink/p/?linkid=2077139)。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Microsoft 365 Defender ポータルの [アラート] セクション" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png":::

Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft 365 Defenderなど、さまざまな Microsoft セキュリティ ソリューションからのアラートがここに表示されます。

既定では、Microsoft 365 Defender ポータルのアラート キューには、過去 30 日間の新規および進行中のアラートが表示されます。 最新のアラートが一覧の一番上に表示されるため、最初にアラートを表示できます。 

既定のアラート キューから [ **フィルター** ] を選択すると、[ **フィルター** ] ウィンドウが表示され、そこからアラートのサブセットを指定できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Microsoft 365 Defender ポータルの [フィルター] セクション。" lightbox="../../media/investigate-alerts/alerts-ss-alerts-filter.png":::

次の条件に従ってアラートをフィルター処理できます。

- 重要度
- 状態
- サービス ソース
- エンティティ (影響を受けた資産)
- 自動調査の状態

## <a name="required-roles-for-defender-for-office-365-alerts"></a>Defender for Office 365アラートに必要なロール

Microsoft Defender for Office 365アラートにアクセスするには、次のいずれかのロールが必要です。

- Azure Active Directory (Azure AD) グローバル ロールの場合:

   - グローバル管理者

   - セキュリティ管理者

   - セキュリティ オペレーター

   - グローバル閲覧者

   - セキュリティ閲覧者

- Office 365 セキュリティ & コンプライアンス ロール グループ

   - コンプライアンス管理者

   - 組織管理 

- [カスタム ロール](custom-roles.md)

## <a name="analyze-an-alert"></a>アラートを分析する

メイン アラート ページを表示するには、アラートの名前を選択します。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Microsoft 365 Defender ポータルでのアラートの詳細" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png":::

[アラートの **管理**] ウィンドウから **[メイン アラート ページを開く**] アクションを選択することもできます。

アラート ページは、次のセクションで構成されます。 

- アラート ストーリー。これは、このアラートに関連するイベントとアラートの連鎖を時系列で示したものです。
- 概要の詳細

アラート ページ全体で、エンティティの横にある省略記号 (**...**) を選択して、アラートを別のインシデントにリンクするなど、使用可能なアクションを表示できます。 使用可能なアクションの一覧は、アラートの種類によって異なります。

### <a name="alert-sources"></a>アラート ソース

Microsoft 365 Defenderアラートは、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、およびMicrosoft Defender for Cloud Apps用のアプリ ガバナンス アドオン。 アラートの先頭に文字が付加されたアラートが表示される場合があります。 次の表は、アラートに付加された文字に基づいてアラート ソースのマッピングを理解するのに役立つガイダンスです。

> [!NOTE]
> - 先頭に追加される GUID は、統合アラート キュー、統合アラート ページ、統合調査、統合インシデントなどの統合エクスペリエンスにのみ固有です。
> - 先頭に付加された文字は、アラートの GUID を変更しません。 GUID に対する唯一の変更は、先頭に追加されたコンポーネントです。

| アラート ソース | 先頭に付加された文字 |
| :---|:--- |
| Microsoft Defender for Office 365 | `fa{GUID}` <br> 例: `fa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Endpoint | `da` または `ed` カスタム検出アラートの場合 <br> |
| Microsoft Defender for Identity | `aa{GUID}` <br> 例: `aa123a456b-c789-1d2e-12f1g33h445h6i` |
| Microsoft Defender for Cloud Apps |`ca{GUID}` <br> 例: `ca123a456b-c789-1d2e-12f1g33h445h6i` |

### <a name="analyze-affected-assets"></a>影響を受ける資産を分析する

**[実行されたアクション]** セクションには、このアラートの影響を受けるメールボックス、デバイス、ユーザーなど、影響を受ける資産の一覧があります。 

[**アクション センターで表示**] を選択して、Microsoft 365 Defender ポータルの **[アクション センター**] の [**履歴**] タブを表示することもできます。 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>アラート ストーリーでアラートのロールをトレースする

アラート ストーリーには、アラートに関連するすべての資産またはエンティティがプロセス ツリー ビューに表示されます。 タイトルのアラートは、選択したアラートのページに最初に移動したときにフォーカスが置かれるアラートです。 アラート ストーリーのアセットは、展開可能でクリック可能です。 アラート ページのコンテキストで適切なアクションを実行できるようにすることで、追加情報を提供し、対応を迅速化します。 

> [!NOTE]
> アラート ストーリー セクションには複数のアラートが含まれている場合があり、選択したアラートの前後に同じ実行ツリーに関連する追加のアラートが表示されます。

### <a name="view-more-alert-information-on-the-details-page"></a>詳細ページでアラート情報を表示する

詳細ページには、選択したアラートの詳細と、それに関連する詳細とアクションが表示されます。 アラート ストーリーで影響を受ける資産またはエンティティのいずれかを選択すると、詳細ページが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。

目的のエンティティを選択すると、詳細ページが変更され、選択したエンティティの種類に関する情報、使用可能な場合の履歴情報、アラート ページから直接このエンティティに対してアクションを実行するオプションが表示されます。

## <a name="manage-alerts"></a>アラートを管理する

アラートを管理するには、アラート ページの概要の詳細セクションで [アラートの **管理** ] を選択します。 1 つのアラートの場合は、[ **アラートの管理** ] ウィンドウの例を次に示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Microsoft 365 Defender ポータルの [アラートの管理] セクション" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png":::

[ **アラートの管理** ] ウィンドウでは、次の項目を表示または指定できます。

- アラートの状態 (新規、解決済み、進行中)。
- アラートが割り当てられているユーザー アカウント。
- アラートの分類:

   - **未設定** (既定値)。

   - **脅威** の種類を持つ真の陽性。 この分類は、実際の脅威を正確に示すアラートに使用します。 脅威の種類を指定すると、セキュリティ チームは脅威パターンを確認し、組織を防御するために行動できます。

   - アクティビティの種類を含む **、情報に関する期待される** アクティビティ。 このカテゴリのオプションを使用して、セキュリティ テスト、赤いチーム アクティビティ、信頼できるアプリやユーザーからの予期される異常な動作のアラートを分類します。

   - 悪意のあるアクティビティがない場合でも作成されたアラートの種類に **対する誤検知**。 アラートを偽陽性として分類すると、検出品質を向上Microsoft 365 Defender役立ちます。

- アラートに関するコメント。

> [!NOTE]
> タグを使用してアラートを管理する 1 つの方法。 Microsoft Defender for Office 365のタグ付け機能は段階的にロールアウトされ、現在プレビュー段階です。 <br>
> 現在、変更されたタグ名は、更新 *後* に作成されたアラートにのみ適用されます。 変更前に生成されたアラートには、更新されたタグ名は反映されません。 

*特定のアラートに似た一連のアラートを* 管理するには、アラート ページの [概要の詳細] セクションの [**INSIGHT**] ボックスで **[類似** したアラートの表示] を選択します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="Microsoft 365 Defender ポータルでアラートを管理する":::

[ **アラートの管理** ] ウィンドウで、関連するすべてのアラートを同時に分類できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="Microsoft 365 Defender ポータルでの関連アラートの管理":::

過去に同様のアラートが既に分類されていた場合は、Microsoft 365 Defender推奨事項を使用して、他のアラートがどのように解決されたかを確認することで、時間を節約できます。 [概要の詳細] セクションで、**おすすめ** を選択します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="アラートの推奨事項を選択する例":::

**[おすすめ**] タブには、調査、修復、防止に関する次のステップのアクションとアドバイスが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="アラートの推奨事項の例":::

## <a name="resolve-an-alert"></a>アラートを解決する

アラートの分析が完了し、解決できたら、アラートまたは類似の **アラートの [アラートの管理**] ウィンドウに移動し、状態を **解決済み** としてマークし、脅威の種類、情報、アクティビティの種類を含む **予想されるアクティビティ、** または **偽陽性** で **True 陽性** として分類します。

アラートを分類すると、検出品質を向上Microsoft 365 Defender役立ちます。

## <a name="use-power-automate-to-triage-alerts"></a>Power Automateを使用してアラートをトリアージする

最新のセキュリティ運用 (SecOps) チームは、効果的に動作するために自動化が必要です。 実際の脅威の捜索と調査に重点を置くために、SecOps チームはPower Automateを使用してアラートの一覧をトリアージし、脅威ではないアラートを排除します。  

### <a name="criteria-for-resolving-alerts"></a>アラートを解決するための条件

- ユーザーが不在時のメッセージを有効にしている

- ユーザーが高リスクとしてタグ付けされていない

両方が true の場合、SecOps はアラートを正当な移動としてマークし、解決します。 通知は、アラートが解決された後、Microsoft Teamsに投稿されます。

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud AppsにConnect Power Automateする

自動化を作成するには、Power AutomateをMicrosoft Defender for Cloud Appsに接続する前に API トークンが必要です。

1. **[設定**] をクリックし、[**セキュリティ拡張機能**] を選択し、[**API トークン**] タブで [**トークンの追加**] をクリックします。

2. トークンの名前を指定し、[ **生成**] をクリックします。 後で必要になるので、トークンを保存します。

### <a name="create-an-automated-flow"></a>自動化されたフローを作成する

詳細なステップ バイ ステップ プロセスについては、 [ここ](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)のビデオを参照してください。

このビデオでは、power Automate を Defender for Cloud Apps に接続する方法についても説明します。

## <a name="next-steps"></a>次の手順

インプロセス インシデントに必要な場合は、 [調査](investigate-incidents.md)を続行します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
