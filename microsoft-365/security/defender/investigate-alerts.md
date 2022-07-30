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
ms.openlocfilehash: 6da9ec9f0d59d04d61d4a957f5a914b06b140fac
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67099219"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defender でアラートを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

>[!Note]
>この記事では、Microsoft 365 Defenderのセキュリティ アラートについて説明します。 ただし、アクティビティ アラートを使用すると、ユーザーが Microsoft 365 で特定のアクティビティを実行したときに、自分または他の管理者に電子メール通知を送信できます。 詳細については、「[アクティビティ アラートの作成 - Microsoft Purview |」を参照してください。Microsoft Docs](../../compliance/create-activity-alerts.md)。

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

   - 組織の管理 

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

## <a name="manage-alerts"></a>アラートの管理

アラートを管理するには、アラート ページの概要の詳細セクションで [アラートの **管理** ] を選択します。 1 つのアラートの場合は、[ **アラートの管理** ] ウィンドウの例を次に示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Microsoft 365 Defender ポータルの [アラートの管理] セクション" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage.png":::

[ **アラートの管理** ] ウィンドウでは、次の項目を表示または指定できます。

- アラートの状態 (新規、解決済み、進行中)。
- アラートが割り当てられているユーザー アカウント。
- アラートの分類:
     - **未設定** (既定値)。
     - **脅威** の種類を持つ真の陽性。 この分類は、実際の脅威を正確に示すアラートに使用します。 この脅威の種類を指定すると、セキュリティ チームに脅威パターンが表示され、組織を防御するアクションが警告されます。
     - アクティビティの種類を含む **、情報に関する期待される** アクティビティ。 このオプションは、技術的に正確で、通常の動作またはシミュレートされた脅威アクティビティを表すアラートに使用します。 一般に、これらのアラートは無視しますが、今後、アクティビティが実際の攻撃者またはマルウェアによってトリガーされる同様のアクティビティに対してこれらのアラートが想定されます。 このカテゴリのオプションを使用して、セキュリティ テスト、赤いチーム アクティビティ、信頼できるアプリやユーザーからの予期される異常な動作のアラートを分類します。
     - **悪意のある** アクティビティがない場合や誤報があった場合でも作成されたアラートの種類に対する誤検知。 このカテゴリのオプションを使用して、通常のイベントまたはアクティビティとして誤って識別されるアラートを悪意のある、または疑わしいものとして分類します。 実際の脅威のキャッチにも役立つ可能性がある"Informational、expected activity" のアラートとは異なり、通常は、これらのアラートを再び表示したくない場合があります。 アラートを偽陽性として分類すると、検出品質を向上Microsoft 365 Defender役立ちます。
- アラートに関するコメント。

>[!NOTE]
> 2022 年 8 月 29 日頃、以前にサポートされていたアラート決定値 ('Apt' と 'SecurityPersonnel') は非推奨になり、API 経由では使用できなくなります。

> [!NOTE]
> タグを使用してアラートを管理する 1 つの方法。 Microsoft Defender for Office 365のタグ付け機能は段階的にロールアウトされ、現在プレビュー段階です。 <br>
> 現在、変更されたタグ名は、更新 *後* に作成されたアラートにのみ適用されます。 変更前に生成されたアラートには、更新されたタグ名は反映されません。 

*特定のアラートに似た一連のアラートを* 管理するには、アラート ページの [概要の詳細] セクションの [**INSIGHT**] ボックスで **[類似** したアラートの表示] を選択します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-manage-select.png" alt-text="Microsoft 365 Defender ポータルでアラートを管理する":::

[ **アラートの管理** ] ウィンドウで、関連するすべてのアラートを同時に分類できます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-select-related.png" alt-text="Microsoft 365 Defender ポータルでの関連アラートの管理":::

過去に同様のアラートが既に分類されていた場合は、Microsoft 365 Defender推奨事項を使用して、他のアラートがどのように解決されたかを確認することで、時間を節約できます。 [概要の詳細] セクションで、[ **推奨事項**] を選択します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations.png" alt-text="アラートの推奨事項を選択する例":::

[ **推奨事項]** タブには、調査、修復、防止に関する次のステップのアクションとアドバイスが表示されます。 次に例を示します。

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-recommendations-example.png" alt-text="アラートの推奨事項の例":::

 
## <a name="suppress-an-alert"></a>アラートを抑制する

セキュリティ オペレーション センター (SOC) アナリストとして、最も重要な問題の 1 つは、毎日トリガーされる膨大な数のアラートをトリアージすることです。 優先度の低いアラートの場合、アナリストは引き続き手動プロセスである傾向があるアラートをトリアージして解決する必要があります。 SOC アナリストの時間は貴重であり、重要度の高いアラートと優先度の高いアラートのみに焦点を当てたいと考えています。

アラート抑制は、事前にアラートを調整および管理する機能を提供します。 これにより、アラート キューが効率化され、特定の予想される組織の動作が発生し、ルール条件が満たされるたびに、アラートを自動的に非表示または解決することでトリアージ時間を節約できます。 

ファイル、プロセス、スケジュールされたタスク、アラートをトリガーするその他の多くの証拠の種類など、"証拠の種類" に基づいてルール条件を作成できます。 ルールを作成した後、ユーザーは、選択したアラートまたはルールの条件を満たすアラートの種類にルールを適用して、アラートを抑制できます。 

> [!NOTE]
> アラートの抑制はお勧めしません。 ただし、特定の状況では、既知の内部ビジネス アプリケーションまたはセキュリティ テストによって予期されるアクティビティがトリガーされ、これらのアラートを表示したくない場合があります。 そのため、アラートの抑制ルールを作成できます。 

### <a name="create-rule-conditions-to-suppress-alerts"></a>アラートを抑制するルール条件を作成する

アラートの抑制ルールを作成するには:

1. 調査対象のアラートを選択します。 メイン アラート ページで、アラート ページの [概要の詳細] セクションで [ **抑制ルールの作成** ] を選択します。 

    :::image type="content" source="../../media/investigate-alerts/suppression-click.png" lightbox="../../media/investigate-alerts/suppression-click.png" alt-text="分離ルールの作成アクションのスクリーンショット。":::

2. [ **抑制ルールの作成** ] ウィンドウで、[ **このアラートの種類のみ** ] を選択して、選択したアラートにルールを適用します。

    ただし、ルールの条件を満たすアラートの種類にルールを適用するには、 **IOC の条件に基づいて [任意のアラートの種類**] を選択します。
 
    IOC は、アラートをトリガーするファイル、プロセス、スケジュールされたタスク、その他の証拠の種類などのインジケーターです。
     
3. [ **IOC** ] セクションで、[ **任意の IOC** ] を選択して、アラートの原因となった "証拠" に関係なくアラートを抑制します。 

    複数のルール条件を設定するには、[ **IOC の選択] を選択します**。 **AND**、**OR**、およびグループ化オプションを使用して、アラートの原因となるこれらの複数の "証拠の種類" の間にリレーションシップを構築します。
 
    1. たとえば、[ **条件** ] セクションで、[トリガーする証拠 **エンティティ ロール: トリガー**]、[ **等しい** ] を選択し、ドロップダウン リストから証拠の種類を選択します。 

    :::image type="content" source="../../media/investigate-alerts/evidence-types-drop-down-list.png" alt-text="[証拠の種類] ドロップダウン リストのスクリーンショット。" lightbox="../../media/investigate-alerts/evidence-types-drop-down-list.png":::

    2. この "証拠" のすべてのプロパティは、次の各フィールドに新しいサブグループとして自動的に設定されます。
    :::image type="content" source="../../media/investigate-alerts/properties-evidence.png" alt-text="証拠の自動入力のプロパティのスクリーンショット。" lightbox="../../media/investigate-alerts/properties-evidence.png" :::

    > [!NOTE]
    > 条件値では大文字と小文字が区別されません。 

    3. 要件に従って 、この "証拠" のプロパティを編集または削除できます (サポートされている場合はワイルドカードを使用)。

    4. ファイルとプロセス以外の AMSI スクリプト、WMI イベント、スケジュールされたタスクは、証拠の種類ドロップダウン リストから選択できる新しく追加された証拠の種類の一部です。
    :::image type="content" source="../../media/investigate-alerts/other-evidence-types.png" alt-text="他の種類の証拠のスクリーンショット。" lightbox="../../media/investigate-alerts/other-evidence-types.png":::

    5. 別の IOC を追加するには、[ **フィルターの追加]** をクリックします。 
    > [!NOTE]
    > アラートの種類を抑制するには、ルール条件に少なくとも 1 つの IOC を追加する必要があります。
    
4. または、**IOC** セクション **で [すべてのアラート 7 関連 IOC に自動入力**] を選択して、すべてのアラート関連の証拠の種類とそのプロパティを [**条件**] セクションに一度に追加することもできます。
    :::image type="content" source="../../media/investigate-alerts/autofill-iocs.png" alt-text="アラート関連のすべての IOC に自動入力するスクリーンショット。" lightbox="../../media/investigate-alerts/autofill-iocs.png":::

5. [ **スコープ** ] セクションで、特定のデバイス、複数のデバイス、デバイス グループ、組織全体、またはユーザーを選択して、[ **条件** ] サブセクションでスコープを設定します。
    > [!NOTE]
    > **スコープ** が **ユーザー** のみに設定されている場合は、管理アクセス許可が必要です。 スコープが **デバイス****、デバイス グループ** と **共に****ユーザー** に設定されている場合、管理アクセス許可は必要ありません。

:::image type="content" source="../../media/investigate-alerts/suppression-choose-scope.png" lightbox="../../media/investigate-alerts/suppression-choose-scope.png" alt-text="[抑制ルールの作成] ウィンドウのスクリーンショット: 条件、スコープ、アクション。":::
 
6. [ **アクション]** セクションで、[ **アラートの非表示]** または [アラートの **解決**] のいずれかの適切なアクションを実行します。
    **名前**、**コメント** と入力し、[**保存**] をクリックします。

7. **今後、IOC がブロックされないようにします。**<br>
抑制ルールを保存したら、表示された **[サプレッション ルールの作成に成功しました** ] ページで、選択した IOC をインジケーターとして "許可リスト" に追加し、今後ブロックされないようにすることができます。 <br>
アラート関連のすべての IOC が一覧に表示されます。 <br>
既定では、抑制条件で選択された IOC が選択されます。
      1. たとえば、許可するファイルを **Select evidence (IOC) に追加して許可** することができます。 既定では、アラートをトリガーしたファイルが選択されます。
      1. 適用するスコープを **選択するスコープを入力します**。 既定では、関連するアラートのスコープが選択されます。
      1. **[保存]** をクリックします。 これで、ファイルは許可リストに含まれているのでブロックされません。

    :::image type="content" source="../../media/investigate-alerts/suppression-2-choose-iocs.png" lightbox="../../media/investigate-alerts/suppression-2-choose-iocs.png" alt-text="抑制ルールの作成が成功したスクリーンショット。 ":::

8.  新しい抑制アラート機能は既定で使用できます。 <br> ただし、[**設定] > [エンドポイント] > [アラート抑制]** に移動し、[**新しい抑制ルールの作成が有効]** トグルをオフにすることで、Microsoft 365 Defender ポータルで以前のエクスペリエンスに戻すことができます。 
 
    :::image type="content" source="../../media/investigate-alerts/suppression-toggle.png" lightbox="../../media/investigate-alerts/suppression-toggle.png" alt-text="抑制ルール作成機能のオン/オフを切り替えるトグルのスクリーンショット。":::

9.  **既存のルールを編集する:** <br> 関連するルールを選択し、[ルールの **編集]** をクリックすると、Microsoft Defender ポータルで常にルールの条件と新しいルールまたは既存のルールの範囲を追加または変更できます。    
    既存のルールを編集するには、[ **新しい抑制ルールの作成が有効]** トグルが有効になっていることを確認します。         

    :::image type="content" source="../../media/investigate-alerts/suppression-toggle-on-edit.png" lightbox="../../media/investigate-alerts/suppression-toggle-on-edit.png" alt-text="抑制ルールの編集のスクリーンショット。":::
  
## <a name="resolve-an-alert"></a>アラートを解決する

アラートの分析が完了し、解決できたら、アラートまたは類似の **アラートの [アラートの管理**] ウィンドウに移動し、状態を **解決済み** としてマークし、脅威の種類、情報、アクティビティの種類を含む **予想されるアクティビティ、** または **偽陽性** で **True 陽性** として分類します。

アラートを分類すると、検出品質を向上Microsoft 365 Defender役立ちます。

## <a name="use-power-automate-to-triage-alerts"></a>Power Automate を使用してアラートをトリアージする

最新のセキュリティ運用 (SecOps) チームは、効果的に動作するために自動化が必要です。 実際の脅威の捜索と調査に専念するために、SecOps チームは Power Automate を使用してアラートの一覧をトリアージし、脅威ではないアラートを排除します。  

### <a name="criteria-for-resolving-alerts"></a>アラートを解決するための条件

- ユーザーが不在時のメッセージを有効にしている

- ユーザーが高リスクとしてタグ付けされていない

両方が true の場合、SecOps はアラートを正当な移動としてマークし、解決します。 通知は、アラートが解決された後、Microsoft Teamsに投稿されます。

### <a name="connect-power-automate-to-microsoft-defender-for-cloud-apps"></a>Power Automate をMicrosoft Defender for Cloud Appsに接続する

自動化を作成するには、Power Automate をMicrosoft Defender for Cloud Appsに接続する前に API トークンが必要です。

1. [**設定] を** クリックし、[**セキュリティ拡張機能**] を選択し、[**API トークン**] タブで [**トークンの追加**] をクリックします。

2. トークンの名前を指定し、[ **生成**] をクリックします。 後で必要になるので、トークンを保存します。

### <a name="create-an-automated-flow"></a>自動化されたフローを作成する

この短いビデオでは、スムーズなワークフローを作成するために自動化が効率的に機能する方法と、Power Automate を Defender for Cloud Apps に接続する方法について説明します。 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn]

## <a name="next-steps"></a>次の手順

インプロセス インシデントに必要な場合は、 [調査](investigate-incidents.md)を続行します。

## <a name="see-also"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの管理](manage-incidents.md)
- [インシデントの調査](investigate-incidents.md)
- [データ損失インシデントを調査する](investigate-dlp.md)