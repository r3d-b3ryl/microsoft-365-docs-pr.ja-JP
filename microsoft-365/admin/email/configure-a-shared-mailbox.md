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
localization_priority: Normal
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
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393993"
---
# <a name="configure-shared-mailbox-settings"></a>共有メールボックスの設定を構成する

共有メールボックス [を作成したら](create-a-shared-mailbox.md)、電子メールの転送や自動返信など、メールボックス ユーザーに対していくつかの設定を構成します。 後で、メールボックス名、メンバー、またはメンバーのアクセス許可など、他の設定を変更することもできます。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>共有メールボックスの名前またはメール エイリアスを変更するか、プライマリ メール アドレスを変更する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[名前]、[メール]、[メール エイリアス] の横にある [編集 **] を選択します**。

3. 新しい名前を入力するか、別のエイリアスを追加します。 プライマリ メール アドレスを変更する場合は、メールボックスに複数のメール エイリアスが必要です。

4. **[保存]** を選択します。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>共有メールボックスに送信されたメールを転送する

共有メールボックスに送信されるメールを転送するために、共有メールボックスにライセンスを割り当てる必要はない。 メッセージは、有効な電子メール アドレスまたは配布リストに転送できます。

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[メール転送の編集 **] を** \> **選択します**。
    
3. トグルを [ **オン] に設定** し、メッセージを転送するメール アドレスを 1 つ入力します。 有効な電子メール アドレスを指定できます。 複数のアドレスに転送するには、アドレスの[](/office365/admin/setup/create-distribution-lists)配布グループを作成し、このボックスにグループの名前を入力する必要があります。
    
4. **[保存]** を選択します。

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>共有メールボックスから自動応答を送信する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[自動返信の編集 **] を** \> **選択します**。
    
3. トグルを **[オン] に** 設定し、組織内または組織外のユーザーに返信を送信するかどうかを選択します。

4. 組織内部のユーザーに送信する返信を入力します。画像は追加できません。テキストのみを入力できます。

5. 組織外のユーザー *にも* 返信を送信する場合は、チェック ボックスをオンにして、返信を取得するユーザーを選択し、テキストを入力します。 組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。

6. **[保存]** を選択します。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>送信済みメール (返信) の表示を全員に許可する

既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。

すべてのユーザーに送信メールの表示を許可する場合は、管理センターで共有メールボックス設定を編集し、[送信されたアイテムの編集] **を** \> **選択します**。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>共有メールボックスが Microsoft メールへのアクセスに使用できるアプリを選択する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[メール アプリの編集] **を** \> **選択します**。

3. メンバーが共有 **メールボックスに** アクセスするために使用できるすべてのアプリのトグルを [オン] に設定します。 使用しないアプリのトグルを **[オフ** ] に設定します。 

4. **[保存]** を選択します。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>訴訟ホールドに共有メールボックスを置く

訴訟ホールドの詳細については、「訴訟ホールドの [作成」を参照してください](../../compliance/create-a-litigation-hold.md)。

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[訴訟ホールドの編集 **] を** \> **選択します**。

3. トグルを On に **設定します**。 

4. 必要に応じて、期間、保留に関するメモ、および詳細を示す URL を入力します。  

5. **[保存]** を選択します。


## <a name="add-or-remove-members"></a>メンバーの追加または削除

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[メンバーの編集] **を** \> **選択します**。

3. 次のいずれかの操作を行います。
   - メンバーを追加するには、[メンバーの **追加] を** 選択し、追加するメンバーを検索または選択し、[保存] を **選択します**。
   - メンバーを削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択し、[保存] を **選択します**。 

4. [保存 **] を再度** 選択します。

## <a name="add-or-remove-permissions-of-members"></a>メンバーのアクセス許可を追加または削除する

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[メンバーのカスタマイズ] \> **アクセス許可を選択します**。

3. メンバー **に対** して変更するアクセス許可の横にある [編集] を選択します。 

4. 次のいずれかの操作を行います。
   - そのアクセス許可を追加のメンバーに付与するには、[アクセス許可の追加] **を選択し**、追加するメンバーを検索または選択し、[保存] を **選択します**。
   - メンバーからアクセス許可を削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択し、[保存] を選択 **します**。 

4. [保存 **] を再度** 選択します。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>グローバル アドレス一覧で共有メールボックスを表示または非表示にする

共有メールボックスをグローバル アドレス一覧に表示しない場合、メールボックスは組織のアドレス一覧には表示されませんが、送信された電子メールは引き続き受信されます。 

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

2. 編集する共有メールボックスを選択し、[グローバル アドレス一覧に表示する]**を選択** \> **します。**

3. トグルを [オン] または **[オフ] に****設定します**。 

4. **[保存]** を選択します。

> [!NOTE]
> 共有メールボックスをアドレス一覧から非表示にすると、新しい共有メールボックスメンバーが、共有メールボックスがアドレス一覧に再び表示されるまで、非表示のメールボックスを Outlook プロファイルに追加できません。 

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)