---
title: 共有メールボックスの設定を構成する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成し、電子メール転送や自動返信など、ユーザーの設定を構成します。
ms.openlocfilehash: 201291adddf588bde955cbba7e2c0075e5ca7c88
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165114"
---
# <a name="configure-shared-mailbox-settings"></a>共有メールボックスの設定を構成する

[共有メールボックスを作成](create-a-shared-mailbox.md)したら、メール転送や自動返信など、メールボックス ユーザーに対していくつかの設定を構成する必要があります。 後で、メールボックス名、メンバー、メンバーのアクセス許可など、他の設定を変更することもできます。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>共有メールボックスの名前または電子メール エイリアスを変更するか、プライマリ電子メール アドレスを変更する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、**名前、電子メール、電子メールエイリアス** の横にある **[編集]** を選択します。

3. 新しい名前を入力するか、別のエイリアスを追加します。 プライマリ電子メール アドレスを変更する場合は、メールボックスに複数のメール エイリアスが必要です。

4. **[保存]** を選択します。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>共有メールボックスに送信されたメールを転送する

共有メールボックスに送信された電子メールを転送するために、ライセンスを割り当てる必要はありません。 有効な電子メール アドレスまたは配布リストにメッセージを転送できます。

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[ **電子メール転送** \> **の編集**] を選択します。
    
3. トグルを **[オン] に** 設定し、メッセージを転送するメール アドレスを 1 つ入力します。 任意の有効な電子メール アドレスを指定できます。 複数のアドレスに転送するには、アドレスの [配布グループを作成](/office365/admin/setup/create-distribution-lists) し、このボックスにグループの名前を入力する必要があります。
    
4. **[保存]** を選択します。

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>共有メールボックスから自動応答を送信する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[ **自動返信** \> **の編集**] を選択します。
    
3. トグルを **[オン] に** 設定し、組織内または組織内外のユーザーに返信を送信するかどうかを選択します。

4. 組織内部のユーザーに送信する返信を入力します。画像は追加できません。テキストのみを入力できます。

5. 組織外のユーザー *にも* 返信を送信する場合は、返信を受け取るユーザーのチェック ボックスをオンにし、テキストを入力します。 組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。

6. **[保存]** を選択します。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>送信済みメール (返信) の表示を全員に許可する

既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。

すべてのユーザーに送信済みメールの表示を許可する場合は、管理センターで共有メールボックスの設定を編集し、[**送信済みアイテム**\>の編集] を選択 **します**。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>共有メールボックスが Microsoft 電子メールにアクセスするために使用できるアプリを選択する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[ **電子メール アプリ** \> **の編集**] を選択します。

3. メンバーが共有メールボックスへのアクセスに使用できるようにするすべてのアプリについて、トグルを **[オン]** に設定します。 使用しないアプリの切り替えを **オフ** に設定します。 

4. **[保存]** を選択します。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>訴訟ホールドに共有メールボックスを配置する

訴訟ホールドの詳細については、「訴訟ホールド [の作成](../../compliance/create-a-litigation-hold.md)」を参照してください。

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[**訴訟ホールド**\>編集] を選択 **します**。

3. トグルを **[オン]** に設定します。 

4. 必要に応じて、期間、保留に関するメモ、および詳細情報を含む URL を入力します。  

5. **[保存]** を選択します。


## <a name="add-or-remove-members"></a>メンバーを追加または削除する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[ **メンバー** \> **の編集**] を選択します。

3. 次のいずれかの操作を行います。
   - メンバーを追加するには、[ **メンバーの追加]** を選択し、追加するメンバーを検索または選択して、[保存] を選択 **します**。
   - メンバーを削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X** ] を選択して、[保存] を選択 **します**。 

4. もう一度 **[保存]** を選択します。

## <a name="add-or-remove-permissions-of-members"></a>メンバーのアクセス許可を追加または削除する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[ **メンバー** \> **のカスタマイズ] アクセス許可** を選択します。

3. メンバーに対して変更するアクセス許可の横にある **[編集]** を選択します。 

4. 次のいずれかの操作を行います。
   - そのアクセス許可を追加のメンバーに付与するには、[ **アクセス許可の追加]** を選択し、追加するメンバーを検索または選択して、[保存] を選択 **します**。
   - メンバーからアクセス許可を削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X** ] を選択して、[保存] を選択 **します**。 

4. もう一度 **[保存]** を選択します。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>グローバル アドレス一覧で共有メールボックスを表示または非表示にする

共有メールボックスをグローバル アドレス一覧に表示しない場合、メールボックスは組織のアドレス一覧には表示されませんが、そのメールボックスに送信された電子メールは引き続き受信されます。 

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[**グローバル アドレス一覧に表示****する編集**] を選択します\>。

3. トグルを **[オン]**  または **[オフ]** に設定します。 

4. **[保存]** を選択します。

> [!NOTE]
> アドレス一覧から共有メールボックスを非表示にすると、新しい共有メールボックス メンバーは、共有メールボックスがアドレス一覧に再び表示されるまで、非表示のメールボックスをOutlook プロファイルに追加できなくなります。 

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックス GWT を作成する](create-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)