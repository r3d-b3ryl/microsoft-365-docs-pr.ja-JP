---
title: 攻撃面の減少 (ASR) ルールをテストする
description: 攻撃面削減 (ASR) ルールのデプロイをテストするためのガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR 展開、ASR の有効化、ASR の構成、ホスト侵入防止システム、保護規則、悪用防止ルール、悪用防止ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、ASR 規則の構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 8bfe3e0d36a02831b5673b92217152ce87804d0a
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601292"
---
# <a name="test-attack-surface-reduction-asr-rules"></a>攻撃面の減少 (ASR) ルールをテストする

攻撃表面縮小 (ASR) ルールのテストは、ルールがルールを有効にする前に基幹業務を妨げるかどうかを判断するのに役立ちます。 小規模で制御されたグループから始めることで、組織全体に展開を拡大するときに、潜在的な作業中断を制限できます。

リング 1 を使用して、攻撃面の縮小 (ASR) ルールの展開を開始します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-testing-steps.png" alt-text="ASR ルールのテスト手順" lightbox="images/asr-rules-testing-steps.png":::
  
## <a name="step-1-test-asr-rules-using-audit"></a>手順 1: 監査を使用して ASR ルールをテストする

テスト フェーズを開始するには、リング 1 のチャンピオン ユーザーまたはデバイスから始めて、監査に設定されたルールを使用して ASR ルールをオンにします。 通常、テスト フェーズ中にトリガーされるルールを決定できるように、すべてのルール (監査) を有効にすることをお勧めします。 監査に設定されたルールは、通常、ルールが適用されるエンティティまたはエンティティの機能には影響しませんが、評価のためにログに記録されたイベントが生成されることに注意してください。エンド ユーザーには影響しません。

### <a name="configure-asr-rules-using-mem"></a>MEM を使用して ASR ルールを構成する

Microsoft エンドポイント マネージャー (MEM) エンドポイント セキュリティを使用して、カスタム ASR ルールを構成できます。

1. [Microsoft エンドポイント マネージャー管理センターを](https://endpoint.microsoft.com/#home)開きます。
2. **Endpoint Security** > **Attack surface reduction** に移動します。
3. **[ポリシーを作成する]** を選択します。
4. **[プラットフォーム**] **で [Windows 10以降**] を選択し、[**プロファイル**] で [**攻撃面の縮小ルール**] を選択します。
  
    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-create-profile.png" alt-text="ASR ルールのプロファイル作成ページ" lightbox="images/asr-mem-create-profile.png":::

5. **[作成]** をクリックします。
6. [**プロファイルの作成**] ウィンドウの [**基本**] タブの [**名前]** にポリシーの名前を追加します。 [ **説明]** に、ASR ルール ポリシーの説明を追加します。
7. [ **構成設定** ] タブの [ **攻撃表面の縮小ルール**] で、すべてのルールを **監査モード** に設定します。

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/asr-mem-configuration-settings.png" alt-text="監査モードへの ASR ルールの構成" lightbox="images/asr-mem-configuration-settings.png":::

    >[!Note]
    >一部の ASR ルール モードの一覧にはバリエーションがあります。 _ブロック_ と _有効化は_ 、同じ機能を提供します。

8. [省略可能][ **スコープ タグ** ] ウィンドウでは、特定のデバイスにタグ情報を追加できます。 また、ロールベースのアクセス制御とスコープ タグを使用して、適切な管理者が適切なIntune オブジェクトに対して適切なアクセスと可視性を持つようにすることもできます。 詳細情報: [Intuneで分散 IT にロールベースのアクセス制御 (RBAC) タグとスコープ タグを使用](/mem/intune/fundamentals/scope-tags)する。
9. [ **割り当て** ] ウィンドウでは、ユーザーまたはデバイス グループにプロファイルを展開または "割り当てる" ことができます。 詳細情報: [Microsoft Intuneでデバイス プロファイルを割り当てる](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. [ **確認と作成** ] ウィンドウで設定を確認します。 [ **作成** ] をクリックしてルールを適用します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-review-create.png" alt-text="[プロファイルの作成] ページ" lightbox="images/asr-mem-review-create.png":::

ASR ルールに対する新しい攻撃面削減ポリシーは、 **エンドポイント セキュリティ |に一覧表示されます。攻撃面の縮小**。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="images/asr-mem-my-asr-rules.png" alt-text=" [攻撃面の縮小] ページ" lightbox="images/asr-mem-my-asr-rules.png":::

## <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>手順 2: Microsoft 365 Defender ポータルの [攻撃対象の縮小ルール] レポート ページについて

ASR ルール レポート ページは、**Microsoft 365 Defender ポータル** > **レポート** > **攻撃サーフェイス削減ルール** にあります。 このページには、次の 3 つのタブがあります。

- Detections
- 構成
- 除外を追加する

### <a name="detections-tab"></a>[検出] タブ

検出された監査とブロックされたイベントの 30 日間のタイムラインを提供します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01.png" alt-text="[攻撃面の縮小ルールの検出] タブ" lightbox="images/asr-defender365-01.png":::

[攻撃面の縮小ルール] ウィンドウには、検出されたイベントの概要がルールごとに表示されます。

>[!Note]
>ASR ルール レポートにはいくつかのバリエーションがあります。 Microsoft は、一貫性のあるエクスペリエンスを提供するために ASR ルール レポートの動作を更新中です。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-01b.png" alt-text="[攻撃面の縮小ルール] ページ" lightbox="images/asr-defender365-01b.png"::: 

[ **検出の表示** ] をクリックして、[検出] タブ **を** 開きます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="攻撃面の縮小ルールの検出" lightbox="images/asr-defender365-reports-detections.png":::

**[GroupBy**] ウィンドウと **[フィルター]** ウィンドウには、次のオプションがあります。

**GroupBy は**、次のグループに設定された結果を返します。

- グループ化なし
- 検出されたファイル
- 監査またはブロック
- Rule
- ソース アプリ
- Device
- User
- Publisher

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-reports-detections.png" alt-text="攻撃面の縮小ルール検出 GroupBy フィルター" lightbox="images/asr-defender365-reports-detections.png":::

**[フィルター** ] で **[ルールのフィルター]** ページが開きます。これにより、選択した ASR ルールのみに結果の範囲を設定できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-filter.png" alt-text="攻撃面の縮小ルールの検出は、ルールに対するフィルター" lightbox="images/asr-defender365-filter.png":::

>[!Note]
>Microsoft Microsoft 365 Security E5 または A5、Windows E5、または A5 ライセンスをお持ちの場合は、次のリンクをクリックすると、Microsoft Defender 365 レポート> [攻撃面の縮小](https://security.microsoft.com/asr?viewid=detections) >検出タブが開きます。

### <a name="configuration-tab"></a>[構成] タブ

コンピューター単位で、ASR ルールの集計状態である[オフ]、[監査]、[ブロック] の一覧。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.png" alt-text="[攻撃表面の縮小ルールの構成] タブとそのページのエントリ" lightbox="images/asr-defender365-configurations.png":::

[構成] タブでは、ASR ルールを確認するデバイスを選択することで、デバイスごとにどの ASR ルールが有効か、どのモードでオンにするかを確認できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-configurations.settings.png" alt-text="攻撃面の縮小ルールが有効でモード" lightbox="images/asr-defender365-configurations.settings.png":::

[**作業の開始**] リンクをクリックすると、Microsoft エンドポイント マネージャー管理センターが開き、ASR のエンドポイント保護ポリシーを作成または変更できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem1.png" alt-text="[概要] ページの *[エンドポイント セキュリティ] メニュー項目" lightbox="images/asr-defender365-05b-mem1.png":::

エンドポイント セキュリティ |[概要]、[ **攻撃面の縮小**] の順に選択します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem2.png" alt-text="MEM の攻撃面の削減" lightbox="images/asr-defender365-05b-mem2.png":::

Endpoint Security |[攻撃面の縮小] ウィンドウが開きます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-05b-mem3.png" alt-text="[エンドポイント セキュリティの攻撃面の縮小] ウィンドウ" lightbox="images/asr-defender365-05b-mem3.png":::

>[!Note]
>Microsoft Defender 365 E5 (または Windows E5?) ライセンスをお持ちであれば、このリンクをクリックすると、Microsoft Defender 365 レポート>攻撃面の縮小> [[構成]](https://security.microsoft.com/asr?viewid=configuration) タブが開きます。

### <a name="add-exclusions"></a>除外を追加する

このタブには、検出されたエンティティ (誤検知など) を除外対象として選択するメソッドが用意されています。 除外が追加されると、予想される影響の概要がレポートに表示されます。

>[!Note]
> Microsoft Defender ウイルス対策 AV の除外は、ASR 規則によって適用されます。  [拡張機能、名前、または場所に基づいて除外を構成して検証](configure-extension-file-exclusions-microsoft-defender-antivirus.md)する方法に関するページを参照してください。

> [!div class="mx-imgBorder"]
> :::image type="content" source="Images/asr-defender365-06d.png" alt-text="検出されたファイルを除外するためのウィンドウ" lightbox="Images/asr-defender365-06d.png":::

> [!Note]
>Microsoft Defender 365 E5 (または Windows E5?) ライセンスをお持ちであれば、このリンクをクリックすると、Microsoft Defender 365 レポート >攻撃面の縮小> [[除外]](https://security.microsoft.com/asr?viewid=exclusions) タブが開きます。

### <a name="use-powershell-as-an-alternative-method-to-enable-asr-rules"></a>ASR ルールを有効にする代替方法として PowerShell を使用する

MEM の代わりに PowerShell を使用すると、監査モードで ASR ルールを有効にして、機能が完全に有効になっている場合にブロックされたアプリのレコードを表示できます。 また、通常の使用時にルールが発生する頻度を把握することもできます。

監査モードで攻撃表面縮小ルールを有効にするには、次の PowerShell コマンドレットを使用します。

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

[攻撃面の縮小ルールの GUID 値](attack-surface-reduction-rules-reference.md)はどこにありますか`<rule ID>`。

監査モードで追加されたすべての攻撃表面縮小ルールを有効にするには、次の PowerShell コマンドレットを使用します。

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> 組織内で攻撃表面縮小ルールがどのように機能するかを完全に監査する場合は、管理ツールを使用してこの設定をネットワーク内のデバイスに展開する必要があります。

グループ ポリシー、Intune、モバイル デバイス管理 (MDM) 構成サービス プロバイダー (CSP) を使用して設定を構成および展開することもできます。 詳細については、主な [攻撃面の縮小ルールに関する](attack-surface-reduction.md) 記事を参照してください。

## <a name="use-windows-event-viewer-review-as-an-alternative-to-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルの [攻撃表面の縮小ルール] レポート ページの代わりに Windows イベント ビューアー レビューを使用する

ブロックされたアプリを確認するには、イベント ビューアーを開き、Microsoft-Windows-Windows Defender/運用ログでイベント ID 1121 をフィルター処理します。 次の表に、すべてのネットワーク保護イベントを示します。

イベント ID | 説明
-|-
 5007 | 設定が変更された場合のイベント
 1121 | 攻撃面の縮小ルールがブロック モードで発生した場合のイベント
 1122 | 攻撃表面の縮小ルールが監査モードで発生した場合のイベント

## <a name="additional-topics-in-this-deployment-collection"></a>このデプロイ コレクションのその他のトピック

[攻撃面の縮小 (ASR) ルールの展開の概要](attack-surface-reduction-rules-deployment.md)

[攻撃面の縮小 (ASR) ルールの展開を計画する](attack-surface-reduction-rules-deployment-plan.md)

[攻撃面の減少 (ASR) ルールを有効にする](attack-surface-reduction-rules-deployment-implement.md)

[攻撃面の減少 (ASR) ルールの運用化](attack-surface-reduction-rules-deployment-operationalize.md)

[攻撃面の減少 (ASR) ルールの参照](attack-surface-reduction-rules-reference.md)
