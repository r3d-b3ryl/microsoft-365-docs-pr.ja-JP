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
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187591"
---
# <a name="create-and-manage-device-tags"></a>デバイス タグの作成と管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスにタグを追加して、論理グループ所属を作成します。 デバイス タグは、ネットワークの適切なマッピングをサポートし、さまざまなタグを添付してコンテキストをキャプチャし、インシデントの一部として動的なリスト作成を有効にできます。 タグは、[デバイス] リスト ビューの **フィルターとして、** またはデバイスをグループ化するために使用できます。 デバイス グループ化の詳細については、「デバイス グループの作成 [と管理」を参照してください](machine-groups.md)。

デバイスにタグを追加するには、次の方法を使用します。

- ポータルの使用
- レジストリ キー値の設定

> [!NOTE]
> タグがデバイスに追加される時間と、デバイスリストとデバイス ページの可用性の間に、いくつかの待機時間が生じ得る場合があります。  

API を使用してデバイス タグを追加するには、「デバイス タグ API を [追加または削除する」を参照してください](add-or-remove-machine-tags.md)。

## <a name="add-and-manage-device-tags-using-the-portal"></a>ポータルを使用してデバイス タグを追加および管理する

1. タグを管理するデバイスを選択します。 次のビューからデバイスを選択または検索できます。

   - **セキュリティ操作ダッシュボード** - [アクティブな通知を含むトップ デバイス] セクションからデバイス名を選択します。
   - **アラート キュー** - 通知キューからデバイス アイコンの横にあるデバイス名を選択します。
   - **[デバイスの** 一覧] - デバイスの一覧からデバイス名を選択します。
   - **[検索]** ボックス - ドロップダウン メニューから [デバイス] を選択し、デバイス名を入力します。

     ファイルビューと IP ビューからアラート ページにアクセスすることもできます。

2. 応答 **アクションの行から** [タグの管理] を選択します。

    ![[タグの管理] ボタンのイメージ](images/manage-tags.png)

3. タグを検索または作成する入力

    ![デバイスにタグを追加するイメージ1](images/new-tags.png)

タグはデバイス ビューに追加され、[デバイス] リスト ビュー **にも反映** されます。 次に、[タグ] フィルター **を使用** して、関連するデバイスの一覧を表示できます。

>[!NOTE]
> かっこを含むタグ名では、フィルター処理が機能しない場合があります。<br>
> 新しいタグを作成すると、既存のタグの一覧が表示されます。 一覧には、ポータルを通じて作成されたタグだけが表示されます。 クライアント デバイスから作成された既存のタグは表示されません。

このビューからタグを削除することもできます。

![デバイスにタグを追加するイメージ2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>レジストリ キーの値を設定してデバイス タグを追加する

>[!NOTE]
> 次のデバイスにのみ適用されます。
>- Windows 10バージョン 1709 以降
>- Windowsサーバー、バージョン 1803 以降
>- Windows Server 2016
>- Windows Server 2012 R2
>- Windows Server 2008 R2 SP1
>- Windows 8.1
>- Windows 7 SP1

> [!NOTE] 
> タグに設定できる最大文字数は 200 文字です。

類似のタグを持つデバイスは、デバイスの特定のリストにコンテキスト アクションを適用する必要がある場合に便利です。

デバイスにタグを追加するには、次のレジストリ キー エントリを使用します。

- レジストリ キー: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- レジストリ キーの値 (REG_SZ): `Group`
- レジストリ キー のデータ: `Name of the tag you want to set`

>[!NOTE]
>デバイス タグは、1 日に 1 回生成されるデバイス情報レポートの一部です。 代わりに、新しいデバイス情報レポートを転送するエンドポイントを再起動することもできます。
> 
> 上記のレジストリ キーを使用して追加されたタグを削除する必要がある場合は、'Group' キーを削除する代わりにレジストリ キー データの内容をクリアします。
