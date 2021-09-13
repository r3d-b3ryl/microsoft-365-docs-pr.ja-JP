---
title: デバイス タグの作成と管理
description: デバイス タグを使用してデバイスをグループ化してコンテキストをキャプチャし、インシデントの一部として動的なリスト作成を有効にする
keywords: タグ、デバイス タグ、デバイス グループ、グループ、修復、レベル、ルール、aad グループ、役割、割り当て、ランク
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e23980133d2fb0c69ca79f6dfdde7656e1961097
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59165031"
---
# <a name="create-and-manage-device-tags"></a>デバイス タグの作成と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスにタグを追加して、論理グループ アフィリエーションを作成します。 デバイス タグはネットワークの適切なマッピングをサポートし、さまざまなタグを添付してコンテキストをキャプチャし、インシデントの一部として動的リストを作成できるようにします。 タグは、[デバイス] リスト ビューの **フィルターとして、** またはデバイスをグループ化するために使用できます。 デバイス グループ化の詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。

デバイスにタグを追加するには、次の方法を使用します。

- ポータルを使用する
- レジストリ キー値を設定する

> [!NOTE]
> タグがデバイスに追加される時間と、デバイスリストとデバイス ページの可用性の間に、いくつかの待機時間が生じ得る場合があります。

API を使用してデバイス タグを追加するには、「[デバイス タグ API の追加または削除](add-or-remove-machine-tags.md)」を参照してください。

## <a name="add-and-manage-device-tags-using-the-portal"></a>ポータルを使用してデバイス タグを追加および管理する

1. タグを管理するデバイスを選択します。 次のいずれかのビューからデバイスを選択または検索できます。

   - **セキュリティ操作ダッシュボード** - [アクティブな通知を含むトップ デバイス] セクションからデバイス名を選択します。
   - **アラート キュー** - アラート キューからデバイス アイコンの横にあるデバイス名を選択します。
   - **デバイス リスト** - デバイスのリストからデバイス名を選択します。
   - **検索ボックス** - ドロップダウン メニューから [デバイス] を選択し、デバイス名を入力します。

     ファイル ビューと IP ビューからアラート ページにアクセスすることもできます。

2. [応答] アクションの行から **[タグの管理]** を選択します。

    :::image type="content" alt-text="[タグの管理] ボタンのイメージ。" source="images/manage-tags-option.png":::

3. タグを検索または作成する入力

    :::image type="content" alt-text="デバイス 1 にタグを追加するイメージ。" source="images/create-new-tag.png":::

タグはデバイス ビューに追加され、[デバイス] リスト ビュー **にも反映** されます。 次に、[タグ] フィルター **を使用** して、関連するデバイスの一覧を表示できます。

> [!NOTE]
> かっこを含むタグ名では、フィルター処理が機能しない場合があります。
>
> 新しいタグを作成すると、既存のタグの一覧が表示されます。 一覧には、ポータルを通じて作成されたタグだけが表示されます。 クライアント デバイスから作成された既存のタグは表示されません。

このビューからタグを削除することもできます。

:::image type="content" alt-text="デバイス 2 にタグを追加するイメージ。" source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>レジストリ キーの値を設定してデバイス タグを追加する

> [!NOTE]
> 次のデバイスにのみ適用されます。
>
> - Windows 10バージョン 1709 以降
> - Windowsサーバー、バージョン 1803 以降
> - Windows Server 2016
> - Windows Server 2012 R2
> - Windows Server 2008 R2 SP1
> - Windows 8.1
> - Windows 7 SP1

> [!NOTE]
> タグに設定できる最大文字数は 200 文字です。

類似のタグを持つデバイスは、デバイスの特定のリストにコンテキスト アクションを適用する必要がある場合に便利です。

デバイスにタグを追加するには、次のレジストリ キー エントリを使用します。

- レジストリ キー: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- レジストリ キーの値 (REG_SZ): `Group`
- レジストリ キー のデータ: `Name of the tag you want to set`

> [!NOTE]
> デバイス タグは、1 日に 1 回生成されるデバイス情報レポートの一部です。 代わりに、新しいデバイス情報レポートを転送するエンドポイントを再起動することもできます。
>
> 上記のレジストリ キーを使用して追加されたタグを削除する必要がある場合は、'Group' キーを削除する代わりにレジストリ キー データの内容をクリアします。
