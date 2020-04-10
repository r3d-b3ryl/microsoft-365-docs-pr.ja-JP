---
title: 共有メールボックスを構成する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: 共有メールボックスを作成したら、電子メールの転送や自動応答など、ユーザーの設定を構成することができます。 後で、メールボックス名やメンバーなどのその他の設定を変更する必要がある場合があります。
ms.openlocfilehash: fc2995dc448c7cb28c13c10d78b57e7141963539
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212023"
---
# <a name="configure-a-shared-mailbox"></a>共有メールボックスを構成する

[共有メールボックスを作成](create-a-shared-mailbox.md)した後で、メールの転送や自動応答などのメールボックスユーザーの設定を構成する必要があります。 後で、メールボックス名、メンバー、またはメンバのアクセス許可などのその他の設定を変更する必要がある場合があります。 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>共有メールボックスの名前または電子メールエイリアスを変更するか、プライマリ電子メールアドレスを変更します。

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[**名前、電子メール、メールエイリアス**] の横にある [**編集**] を選択します。

3. 新しい名前を入力するか、別のエイリアスを追加します。 プライマリ電子メールアドレスを変更する場合は、メールボックスに複数の電子メールエイリアスを設定する必要があります。

4. [**保存**] を選択します。

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>共有メールボックスに送信されたメールを転送する

送信された電子メールを転送するために、共有メールボックスにライセンスを割り当てる必要はありません。 メッセージを任意の有効な電子メールアドレスまたは配布リストに転送できます。

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[**電子メール転送** \> **編集**] を選択します。
    
3. **[オン**] に切り替え、メッセージを転送するメールアドレスを1つ入力します。 任意の有効な電子メールアドレスを指定できます。 複数のアドレスに転送するには、アドレスの[配布グループを作成](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide)し、このボックスにグループの名前を入力する必要があります。
    
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

2. 編集する共有メールボックスを選択し、[**自動応答** \>の**編集**] を選択します。
    
3. **[オン**] の切り替えを設定し、組織内または組織外のユーザーに返信を送信するかどうかを選択します。

4. 組織内のユーザーに送信する返信を入力します。 画像、テキストのみを追加することはできません。

5. 組織外のユーザーに*も*返信を送信する場合は、チェックボックスをオンにして返信を取得し、テキストを入力します。 組織内のユーザーには送信せず、組織外のユーザーにのみ送信する方法はありません。

6. [**保存**] を選択します。

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>送信済みメール (返信) の表示を全員に許可する

既定では、共有メールボックスから送信されたメッセージは、共有メールボックスの [送信済みアイテム] フォルダーには保存されません。代わりに、メッセージを送信したユーザーの [送信済みアイテム] フォルダーに保存されます。

すべてのユーザーに送信済みメールの表示を許可する場合は、管理センターで、共有メールボックスの設定を編集して、[**送信済みアイテム** \>の**編集**] を選択します。


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-office-365-email"></a>共有メールボックスが Office 365 電子メールへのアクセスに使用できるアプリを選択する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[**電子メールアプリ** \>の**編集**] を選択します。

3. メンバーが共有メールボックスへのアクセスに使用できるようにするすべてのアプリのトグルを **[オン**にする。 使用しないアプリについては、[**オフ**にする (非表示) に設定します。 

4. [**保存**] を選択します。


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>訴訟ホールドに共有メールボックスを配置する

訴訟ホールドの詳細については、「[訴訟ホールドを作成](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)する」を参照してください。

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択して、[**訴訟ホールド** \> **編集**] を選択します。

3. トグルを**オンに**設定します。 

4. 必要に応じて、期間、s に関するメモ、および詳細情報を含む URL を入力します。  

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

2. 編集する共有メールボックスを選択し、[**メンバー** \>の**編集**] を選択します。

3. 次のいずれかの操作を行います。
   - メンバーを追加するには、[**メンバーの追加**] を選択し、追加するメンバーを検索または選択して、[**保存**] を選択します。
   - メンバーを削除するには、検索ボックスを使用してメンバーを検索します。必要に応じて、メンバーの名前の横にある**X**を選択し、[**保存**] を選択します。 

4. [**保存**] をもう一度選択します。

## <a name="add-or-remove-permissions-of-members"></a>メンバーの権限を追加または削除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[**メンバー** \> ] [**アクセス許可のカスタマイズ**] の順に選択します。

3. メンバーに対して変更する権限の横にある [**編集**] を選択します。 

4. 次のいずれかの操作を行います。
   - 追加のメンバーにアクセス許可を付与するには、[**アクセス許可の追加**] を選択し、追加するメンバーを検索または選択して、[**保存**] を選択します。
   - メンバーからアクセス許可を削除するには、検索ボックスを使用してメンバーを検索します。必要に応じて、メンバーの名前の横にある**X**を選択し、[**保存**] を選択します。 

4. [**保存**] をもう一度選択します。

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>グローバルアドレス一覧で共有メールボックスを表示または非表示にする

共有メールボックスをグローバルアドレス一覧に表示しないように選択した場合、そのメールボックスは組織のアドレス一覧に表示されませんが、送信されたメールは引き続き受信します。 

::: moniker range="o365-worldwide"

1. 管理センターで、**[グループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページの順に移動します。

::: moniker-end 

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">[管理センター]</a> で、**[グループ]** > **[共有メールボックス]** ページの順に移動します。 

::: moniker-end

2. 編集する共有メールボックスを選択し、[**グローバルアドレス一覧** \>の**編集**] で [表示] を選択します。

3. トグルを**オン**または**オフ**にします。 

4. [**保存**] を選択します。

> [!NOTE]
> 共有メールボックスをアドレス一覧に表示しないようにすると、共有メールボックスがアドレス一覧に再び表示されるまで、新しい共有メールボックスのメンバーが非表示のメールボックスを Outlook プロファイルに追加できなくなります。 

## <a name="related-articles"></a>関連記事

[共有メールボックスについて](about-shared-mailboxes.md)

[共有メールボックスを作成する](create-a-shared-mailbox.md)

[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)

[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md)

[共有メールボックスの問題を解決する](resolve-issues-with-shared-mailboxes.md)
