---
title: セキュリティに関する推奨事項の例外を作成して表示する - 脅威と脆弱性の管理
description: 脅威と脆弱性の管理のセキュリティに関する推奨事項の例外を作成して監視します。
keywords: Microsoft Defender for Endpoint tvm 修復、Microsoft Defender for Endpoint tvm、脅威と脆弱性の管理、脅威& 脆弱性の管理、脅威& 脆弱性の管理 修復、tvm 修復 Intune、tvm 修復 sccm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 00d7afd9daec71a14d4b789d1d6dcfe5eaf07d83
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477195"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a>セキュリティに関する推奨事項の例外を作成して表示する - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

現時点で推奨事項が関連していない場合の修復要求の代わりに、推奨事項の例外を作成できます。 組織にデバイス グループがある場合は、特定のデバイス グループに対して例外のスコープを設定できます。 例外は、選択したデバイス グループに対して作成することも、過去と現在のすべてのデバイス グループに対して作成することもできます。

推奨事項に対して例外が作成されると、例外期間が終了するまで推奨事項はアクティブになりません。 推奨事項の状態は、 **完全な例外** または **部分例外** (デバイス グループ別) に変更されます。

## <a name="permissions"></a>アクセス許可

例外を管理できるのは、"例外処理" アクセス許可を持つユーザーのみです (作成または取り消しを含む)。 [RBAC ロールの詳細については、こちらを参照してください](user-roles.md)。

:::image type="content" source="images/tvm-exception-permissions.png" alt-text="例外処理アクセス許可" lightbox="images/tvm-exception-permissions.png":::

## <a name="create-an-exception"></a>例外を作成する

例外を作成するセキュリティに関する推奨事項を選択し、 **例外オプション** を選択してフォームに入力します。

:::image type="content" source="images/tvm-exception-options.png" alt-text="セキュリティに関する推奨事項ポップアップの [例外オプション] ボタンの場所" lightbox="images/tvm-exception-options.png":::

### <a name="exception-by-device-group"></a>デバイス グループ別の例外

現在のすべてのデバイス グループに例外を適用するか、特定のデバイス グループを選択します。 今後のデバイス グループは例外に含まれません。 既に例外が発生しているデバイス グループは一覧に表示されません。 特定のデバイス グループのみを選択した場合、推奨事項の状態は "アクティブ" から "部分的な例外" に変わります。 すべてのデバイス グループを選択すると、状態は "完全な例外" に変わります。

:::image type="content" source="images/tvm-exception-device-group-500.png" alt-text="[デバイス グループ] ドロップダウン" lightbox="images/tvm-exception-device-group-500.png":::

#### <a name="filtered-views"></a>フィルター処理されたビュー

いずれかの脅威と脆弱性の管理 ページでデバイス グループでフィルター処理した場合、フィルター処理されたデバイス グループのみがオプションとして表示されます。

これは、脅威と脆弱性の管理 ページのいずれかでデバイス グループでフィルター処理するボタンです。

:::image type="content" source="images/tvm-selected-device-groups.png" alt-text="選択したデバイス グループ フィルター" lightbox="images/tvm-selected-device-groups.png":::

フィルター処理されたデバイス グループを含む例外ビュー:

:::image type="content" source="images/tvm-exception-device-filter500.png" alt-text="フィルター処理されたデバイス グループのドロップダウン" lightbox="images/tvm-exception-device-filter500.png":::

#### <a name="large-number-of-device-groups"></a>デバイス グループの数が多い

組織に 20 を超えるデバイス グループがある場合は、フィルター処理されたデバイス グループ オプションの横にある **[編集]** を選択します。

:::image type="content" source="images/tvm-exception-edit-groups.png" alt-text="多数のグループを編集する手順" lightbox="images/tvm-exception-edit-groups.png":::

ポップアップが表示され、含めるデバイス グループを検索して選択できます。 [検索] の下にあるチェック マーク アイコンを選択して、すべてオン/オフにします。

:::image type="content" source="images/tvm-exception-device-group-flyout-400.png" alt-text="大きなデバイス グループのポップアップ" lightbox="images/tvm-exception-device-group-flyout-400.png":::

### <a name="global-exceptions"></a>グローバル例外

グローバル管理者のアクセス許可がある場合は、グローバル例外を作成して取り消すことができるようになります。 組織内 **のすべての** 現在および将来のデバイス グループに影響を与え、同様のアクセス許可を持つユーザーのみが変更できます。 推奨事項の状態は"アクティブ" から "完全な例外" に変わります。

:::image type="content" source="images/tvm-exception-global.png" alt-text="グローバル例外オプション" lightbox="images/tvm-exception-global.png":::

次の点に注意してください。

- 推奨事項がグローバル例外の下にある場合、デバイス グループに対して新しく作成された例外は、グローバル例外の有効期限が切れたか取り消されるまで中断されます。 その後、新しいデバイス グループの例外は有効期限が切れるまで有効になります。
- 推奨事項に特定のデバイス グループの例外が既に存在し、グローバル例外が作成されている場合、デバイス グループの例外は期限切れになるか、グローバル例外が期限切れになる前に取り消されるまで中断されます。

### <a name="justification"></a>妥当性

問題のセキュリティに関する推奨事項を修復する代わりに、ファイルする必要がある例外の理由を選択します。 理由コンテキストに入力し、例外期間を設定します。

次の一覧では、例外オプションの背後にある理由について詳しく説明します。

- **サード パーティコントロール** - サード パーティ製品またはソフトウェアがこの推奨事項に既に対処しています。 この理由の種類を選択すると、リスクが減るため、露出スコアが低下し、セキュリティスコアが向上します
- **代替軽減策** - 内部ツールは既にこの推奨事項に対処しています。 この理由の種類を選択すると、リスクが減るため、露出スコアが低下し、セキュリティスコアが向上します。
- **受け入れられたリスク** - リスクが低い、または推奨事項の実装がコストがかかりすぎる
- **計画修復 (猶予期間)** - 既に計画されていますが、実行または承認を待機しています

## <a name="view-all-exceptions"></a>すべての例外を表示する

**[修復**] ページの [**例外**] タブに移動します。 理由、種類、状態でフィルター処理できます。

 例外を選択してポップアップを開き、詳細を表示します。 デバイス グループごとの例外には、エクスポートできる例外が含まれるすべてのデバイス グループの一覧が含まれます。 関連する推奨事項を表示したり、例外を取り消したりすることもできます。

:::image type="content" source="images/tvm-exception-view.png" alt-text="[修復] ページの [例外] タブ" lightbox="images/tvm-exception-view.png":::

## <a name="how-to-cancel-an-exception"></a>例外を取り消す方法

例外を取り消すには、[**修復**] ページの [**例外**] タブに移動します。 例外を選択します。

すべてのデバイス グループまたはグローバル例外の例外を取り消すには、[ **すべてのデバイス グループの例外のキャンセル] ボタンを** 選択します。 アクセス許可を持つデバイス グループの例外のみを取り消すことができるようになります。

:::image type="content" source="images/tvm-exception-cancel.png" alt-text="[キャンセル] ボタン" lightbox="images/tvm-exception-cancel.png":::

### <a name="cancel-the-exception-for-a-specific-device-group"></a>特定のデバイス グループの例外を取り消す

特定のデバイス グループを選択して、その例外を取り消します。 デバイス グループにポップアップが表示され、[ **例外のキャンセル]** を選択できます。

:::image type="content" source="images/tvm-exception-device-group-hover.png" alt-text="特定のデバイス グループを選択する手順" lightbox="images/tvm-exception-device-group-hover.png":::

## <a name="view-impact-after-exceptions-are-applied"></a>例外が適用された後の影響を表示する

[セキュリティ おすすめ] ページで、[**列のカスタマイズ**] を選択し、[**公開されたデバイス (例外の後) と影響 (例外の後)]** のチェック ボックスをオンにします。

:::image type="content" source="images/tvm-after-exceptions.png" alt-text="列のカスタマイズ オプション" lightbox="images/tvm-after-exceptions.png":::

公開されたデバイス (例外後) 列には、例外が適用された後も脆弱性にさらされている残りのデバイスが表示されます。 公開に影響を与える例外の理由には、"サード パーティコントロール" と "代替軽減策" が含まれます。 その他の理由により、デバイスの露出が減るわけではありません。また、引き続き公開されていると見なされます。

影響 (例外後) は、例外が適用された後の露出スコアまたはセキュリティスコアへの残りの影響を示します。 スコアに影響を与える例外の理由には、"サード パーティコントロール" と "代替軽減策" が含まれます。 その他の理由により、デバイスの露出が減るわけではないため、露出スコアとセキュリティスコアは変わりません。

:::image type="content" source="images/tvm-after-exceptions-table.png" alt-text="テーブル内の列" lightbox="images/tvm-after-exceptions-table.png":::

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [脆弱性を修復する](tvm-remediation.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [暴露スコア](tvm-exposure-score.md)
- [デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)
