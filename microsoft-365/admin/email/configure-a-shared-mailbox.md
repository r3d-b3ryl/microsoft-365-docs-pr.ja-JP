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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成したら、メールの転送や自動返信など、ユーザーに対していくつかの設定を構成する必要があります。 後で、メールボックス名やメンバーなど、他の設定を変更することもできます。
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926608"
---
# <a name="configure-shared-mailbox-settings"></a>共有メールボックスの設定を構成する

共有メールボックス [を作成したら](create-a-shared-mailbox.md)、メールの転送や自動応答など、メールボックス ユーザーに対していくつかの設定を構成する必要があります。 後で、メールボックス名、メンバー、メンバーのアクセス許可など、他の設定を変更することもできます。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>共有メールボックスの名前または電子メール エイリアスを変更するか、プライマリ メール アドレスを変更する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[名前、電子メール、電子メール エイリアス] の横にある [編集 **] を選択します**。

3. 新しい名前を入力するか、別のエイリアスを追加します。 プライマリ メール アドレスを変更する場合は、メールボックスに複数の電子メール エイリアスが必要です。

4. [**保存**] を選択します。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>共有メールボックスに送信されたメールを転送する

送信されたメールを転送するために、共有メールボックスにライセンスを割り当てる必要はない。 メッセージは、有効な電子メール アドレスまたは配布リストに転送できます。

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[電子メール転送の編集] **を** \> **選択します**。
    
3. トグルを **[オン] に設定** し、メッセージの転送先のメール アドレスを 1 つ入力します。 任意の有効な電子メール アドレスを指定できます。 複数のアドレスに転送するには、アドレスの[](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists)配布グループを作成し、このボックスにグループの名前を入力する必要があります。
    
4. [**保存**] を選択します。

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>共有メールボックスから自動応答を送信する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[自動返信の編集 **] を** \> **選択します**。
    
3. トグルを **[オン**] に設定し、組織内のユーザーまたは組織外のユーザーに返信を送信するかどうかを選択します。

4. 組織内のユーザーに送信する返信を入力します。 画像を追加できるのは、テキストのみです。

5. 組織外 *のユーザーにも* 返信を送信する場合は、返信を受け取るユーザーのチェック ボックスをオンにして、テキストを入力します。 組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。

6. [**保存**] を選択します。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>送信済みメール (返信) の表示を全員に許可する

既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。

送信されたメールの表示をすべてのユーザーに許可する場合は、管理センターで共有メールボックスの設定を編集し、[送信されたアイテムの編集] **を選択** \> **します**。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>共有メールボックスが Microsoft メールへのアクセスに使用できるアプリを選択する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[メール アプリの編集] **を** \> **選択します**。

3. メンバーが共有 **メールボックス** にアクセスするために使用できるすべてのアプリのトグルを [オン] に設定します。 使用しないアプリのトグルを **[オフ** ] に設定します。 

4. [**保存**] を選択します。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>共有メールボックスを訴訟ホールドの対象に設定する

訴訟ホールドの詳細については、「訴訟ホールドの作成 [」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)。

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[訴訟ホールドの編集 **] を** \> **選択します**。

3. トグルをオンに **設定します**。 

4. 必要に応じて、期間、保留に関するメモ、および詳細を含む URL を入力します。  

5. [**保存**] を選択します。


## <a name="add-or-remove-members"></a>メンバーを追加または削除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[メンバーの編集] **を** \> **選択します**。

3. 次のいずれかの操作を行います。
   - メンバーを追加するには、[メンバーの追加 **] を** 選択し、追加するメンバーを検索または選択して、[保存] を選択 **します**。
   - メンバーを削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択して、[保存] を選択 **します**。 

4. [保存 **] を再び** 選択します。

## <a name="add-or-remove-permissions-of-members"></a>メンバーのアクセス許可を追加または削除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[メンバーのカスタマイズ] アクセス **許可** \> **を選択します**。

3. メンバー **に対** して変更するアクセス許可の横にある [編集] を選択します。 

4. 次のいずれかの操作を行います。
   - 追加のメンバーにアクセス許可を付与するには、[アクセス許可の追加] **を選択し**、追加するメンバーを検索または選択して、[保存] を選択 **します**。
   - メンバーからアクセス許可を削除するには、[検索] ボックスを使用して必要に応じてメンバーを検索し、メンバーの名前の横にある **[X]** を選択して、[保存] を選択 **します**。 

4. [保存 **] を再び** 選択します。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>グローバル アドレス一覧で共有メールボックスを表示または非表示にする

共有メールボックスをグローバル アドレス一覧に表示しない場合、メールボックスは組織のアドレス一覧に表示されませんが、そのメールボックスに送信された電子メールを受信します。 

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[グローバル アドレス一覧に **表示する** 編集] を \> **選択します**。

3. トグルをオンまたは **オフに****設定します**。 

4. [**保存**] を選択します。

> [!NOTE]
> 共有メールボックスをアドレス一覧から非表示にすると、共有メールボックスがアドレス一覧に再び表示されるまで、新しい共有メールボックスメンバーが非表示のメールボックスを Outlook プロファイルに追加することは不可能になります。 

## <a name="related-articles"></a>関連記事

[共有メールボックスについて](about-shared-mailboxes.md)

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md)

[共有メールボックスの問題を解決する](resolve-issues-with-shared-mailboxes.md)
