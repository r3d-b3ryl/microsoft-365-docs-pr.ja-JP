---
title: デバイス タグの作成と管理
description: デバイス タグを使用してデバイスをグループ化してコンテキストをキャプチャし、インシデントの一部として動的リストの作成を有効にする
keywords: タグ, デバイス タグ, デバイス グループ, グループ, 修復, レベル, ルール, aad グループ, ロール, 割り当て, ランク
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b0b94e4905a780be9a608c8e91967b47a4db7160
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64465753"
---
# <a name="create-and-manage-device-tags"></a>デバイス タグの作成と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスにタグを追加して、論理グループ アフィリエーションを作成します。 デバイス タグはネットワークの適切なマッピングをサポートし、さまざまなタグを添付してコンテキストをキャプチャし、インシデントの一部として動的リストを作成できるようにします。 タグは、[ **デバイス インベントリ** ] ビューのフィルターとして、またはデバイスをグループ化するために使用できます。 デバイス グループの詳細については、「デバイス [グループの作成と管理](machine-groups.md)」を参照してください。

次の方法を使用して、デバイスにタグを追加できます。

- ポータルを使用する
- レジストリ キー値を設定する

> [!NOTE]
> タグがデバイスに追加されてから、デバイスの一覧とデバイス ページの可用性までの間に、ある程度の待機時間が生じることがあります。

API を使用してデバイス タグを追加するには、「[デバイス タグ API の追加または削除](add-or-remove-machine-tags.md)」を参照してください。

## <a name="add-and-manage-device-tags-using-the-portal"></a>ポータルを使用してデバイス タグを追加および管理する

1. タグを管理するデバイスを選択します。 次のいずれかのビューからデバイスを選択または検索できます。

   - **セキュリティ操作ダッシュボード** - [アクティブなアラートを含む上位デバイス] セクションからデバイス名を選択します。
   - **アラート キュー** - アラート キューからデバイス アイコンの横にあるデバイス名を選択します。
   - **デバイス インベントリ** - デバイスの一覧からデバイス名を選択します。
   - **検索ボックス** - ドロップダウン メニューから [デバイス] を選択し、デバイス名を入力します。

     ファイル ビューと IP ビューからアラート ページにアクセスすることもできます。

2. 応答アクションの行から [ **タグの管理** ] を選択します。

    :::image type="content" source="images/manage-tags-option.png" alt-text="[タグの管理] ボタンの画像" lightbox="images/manage-tags-option.png":::
    

3. タグを検索または作成する型

    :::image type="content" source="images/create-new-tag.png" alt-text="device1 にタグを追加する" lightbox="images/create-new-tag.png":::

タグはデバイス ビューに追加され、 **デバイス インベントリ** ビューにも反映されます。 その後、 **タグ** フィルターを使用して、関連するデバイスの一覧を表示できます。

> [!NOTE]
> かっこを含むタグ名では、フィルター処理が機能しない可能性があります。
>
> 新しいタグを作成すると、既存のタグの一覧が表示されます。 この一覧には、ポータルを介して作成されたタグのみが表示されます。 クライアント デバイスから作成された既存のタグは表示されません。

このビューからタグを削除することもできます。

:::image type="content" source="images/new-tag-label-display.png" alt-text="device2 にタグを追加する" lightbox="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>レジストリ キーの値を設定してデバイス タグを追加する

> [!NOTE]
> 次のデバイスにのみ適用されます。
>
> - Windows 11
> - Windows 10バージョン 1709 以降
> - Windows Server バージョン 1803 以降
> - Windows Server 2016
> - Windows Server 2012 R2
> - Windows Server 2008 R2 SP1
> - Windows 8.1
> - Windows 7 SP1

> [!NOTE]
> タグで設定できる最大文字数は 200 文字です。

同様のタグを持つデバイスは、デバイスの特定のリストにコンテキスト アクションを適用する必要がある場合に便利です。

次のレジストリ キー エントリを使用して、デバイスにタグを追加します。

- レジストリ キー: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- レジストリ キーの値 (REG_SZ): `Group`
- レジストリ キー データ: `Name of the tag you want to set`

> [!NOTE]
> デバイス タグは、1 日に 1 回生成されるデバイス情報レポートの一部です。 別の方法として、新しいデバイス情報レポートを転送するエンドポイントを再起動することもできます。
>
> 上記のレジストリ キーを使用して追加されたタグを削除する必要がある場合は、'Group' キーを削除するのではなく、レジストリ キー データの内容をクリアします。
