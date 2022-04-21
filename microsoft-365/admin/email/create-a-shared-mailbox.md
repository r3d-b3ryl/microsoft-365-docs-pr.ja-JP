---
title: 共有メールボックスを作成する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: 共有メールボックスを作成すると、社内の複数のユーザーが 1 つのメール アドレスに送付されたメールを閲覧したり、回答したりできます。
ms.openlocfilehash: 38e7e1c1371c83fd5b55105bbd91485e2b6c26a3
ms.sourcegitcommit: dc415d784226c77549ba246601f34324c4f94e73
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64915953"
---
# <a name="create-a-shared-mailbox"></a>共有メールボックスを作成する 

> [!NOTE]
> 組織でハイブリッド Exchange 環境を使用する場合は、オンプレミスの <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>を使用して、共有メールボックスを作成して管理する必要があります。「[Exchange 管理センターで共有メールボックスを作成する](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)」を参照してください。
>
> 共有メールボックスと Outlook 用 Microsoft 365 グループのどちらを作成すればよいかわからない場合は、「[グループを比較する](../create-groups/compare-groups.md)」のガイダンスを参照してください。 現在、共有メールボックスを Microsoft 365 グループに移行することはできません。 この機能をご希望の場合は、[こちらから投票](https://go.microsoft.com/fwlink/?linkid=871518)してお知らせください。

共有メールボックスの作成は簡単なので、ユーザーのグループが共通のメール アドレス (info@contoso.com など) を監視して、そこからメールを送信することができます。共有メールボックスに送信されたメッセージにグループのユーザーが返信すると、そのメールは、個別のユーザーからではなく共有メールボックスから送信されたように表示されます。

共有メールボックスには共有の予定表も含まれています。全員が予定を入力できる場所として、共有の予定表を利用したい小規模企業は数多くあります。たとえば、客先に訪問する社員が 3 人いる場合、全員で共有の予定表を使用して予定を入力できます。これで、誰がどこにいるのかが常にわかるようになります。

共有メールボックスを作成する前に、「[共有メールボックスについて](about-shared-mailboxes.md)」を読んで詳細をご確認ください。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="create-a-shared-mailbox-and-add-members"></a>共有メールボックスを作成し、メンバーを追加する
  
1. グローバル管理者アカウント、または Exchange の管理者アカウントでサインインします。"**このページへのアクセス許可がないため、この操作を実行できません**" というメッセージが表示される場合、そのユーザーは管理者ではありません。 

::: moniker range="o365-worldwide"

2. 管理センターで、**[チームとグループ]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">[共有メールボックス]</a> ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

2. [管理センター](https://go.microsoft.com/fwlink/p/?linkid=850627)で、**[チームとグループ]** \> **[共有メールボックス]** ページに移動します。

::: moniker-end
    
3. **[共有メールボックス]** ページで、**[+ 共有メールボックスを追加]** を選択します。 共有メールボックスの名前を入力します。 メール アドレスが選択されますが、必要に応じて編集できます。
    
    ![共有メールボックスに名前を付けます。](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. **[変更を保存]** を選択します。メンバーを追加できるようになるまで、数分かかる場合があります。

5. **[次のステップ]** で、**[このメールボックスにメンバーを追加する]** を選択します。メンバーは、この共有メールボックスへの受信メールと送信した返信を表示できるようになります。

   ![[メンバーの追加] を選択します。](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. **[+ メンバーの追加]** ボタンを選択します。この共有メールボックスを使用するユーザーの横にチェック マークを付けて、**[保存]** を選択します。

   ![共有メールボックスにメンバーを割り当てます。](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. **[閉じる]** を選択します。

これで共有メールボックスを作成できました。共有の予定表も含まれています。 次の手順として、「[共有メールボックス アカウントのサインインをブロックする](#block-sign-in-for-the-shared-mailbox-account)」に進みます。

## <a name="which-permissions-should-you-use"></a>使用するアクセス許可

共有メールボックスと一緒に以下のアクセス許可が使用できます。

- **[フル アクセス]**: [フル アクセス] アクセス許可を使用すれば、共有メールボックスを開いて、そのメールボックスの所有者として作業できます。共有メールボックスにアクセスした後、予定表アイテムを作成したり、メール メッセージの読み取り、表示、削除、変更を行ったり、タスクと予定表の連絡先を作成したりできます。ただし、[フル アクセス] アクセス許可を持っているユーザーは、[メールボックス所有者として送信する] または [代理人として送信する] アクセス許可も持っている場合に限り、共有メールボックスから電子メールを送信できます。

- **[メールボックス所有者として送信する]**: [メールボックス所有者として送信する] アクセス許可を使用すれば、メールの送信時に共有メールボックスを代理で処理できます。たとえば、Katerina がマーケティング部門の共有メールボックスにログインして、メールを送信する場合、そのメールはマーケティング部門が送信したように見えます。

- **[代理人として送信する]**: [代理人として送信する] アクセス許可を使用すれば、共有メールボックスの代わりに電子メールを送信できます。たとえば、John が共有メールボックス Reception Building 32 にログインして電子メールを送信すると、メールが「Reception Building 32 の代わりに John」によって送信されたように見えます。EAC では [代理人として送信する] アクセス許可を付与できないため、 **Set-Mailbox** コマンドレットを _GrantSendonBehalf_ パラメーターと一緒に使用する必要があります。

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a>EAC を使用して共有メールボックスの委任を編集する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>で、**[受信者]**\>**[メールボックス]** の順に移動します。 共有メールボックスを選択し、**[編集]** ![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png) を選択します。

2. **[メールボックスのアクセス許可]** で、**[メールボックス委任の管理]** を選択します。

3. [フル アクセス] および [メールボックス所有者として送信する] アクセス許可を付与または削除するには、**[追加]** ![[追加] アイコン](../../media/ITPro-EAC-AddIcon.png)または **[削除]** ![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)を選択して、アクセス許可を付与するユーザーを選択します。

   > [!NOTE]
   > フル アクセスのアクセス許可を使用すれば、ユーザーはメールボックスを開き、その中でアイテムを作成/変更することができます。「差出人を指定して送信する」アクセス許可を使用すれば、メールボックスの所有者以外のユーザーでも、この共有メールボックスから電子メールを送信することができます。共有メールボックスを正常に操作するには、両方のアクセス許可が必要です。

4. **[保存]** を選択し、変更内容を保存します。


## <a name="block-sign-in-for-the-shared-mailbox-account"></a>共有メールボックス アカウントのサインインをブロックする

どの共有メールボックスにも、対応するユーザー アカウントがあります。 共有メールボックスを作成する際に、パスワードの入力を求められなかったことにご注意ください。 このアカウントにはパスワードが設定されていますが、そのパスワードはシステムで生成され、ユーザーにはわかりません。 ユーザーは、そのアカウントを使用して共有メールボックスにログインする訳ではありません。

では、管理者が共有メールボックスのユーザー アカウントのパスワードをリセットした場合はどうなりますか。 また、攻撃者がその共有メールボックス アカウントの資格情報にアクセスできるようになった場合はどうなるでしょうか。 そうなれば、そのユーザー アカウントで共有メールボックスにログインして、メールを送信することが可能になってしまいます。 これを防ぐために、この共有メールボックスに関連付けられているアカウントのサインインをブロックする必要があります。

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> の順に選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> の順に選択します。
::: moniker-end

2. ユーザー アカウントの一覧から、共有メールボックスのアカウントを探します (例: フィルターを **[ライセンス未付与のユーザー]** に変更する)。

3. そのユーザーを選択してプロパティ ウィンドウを開き、**[このユーザーをブロックする]** アイコンを選択します ![[このユーザーをブロックする] アイコンのスクリーンショット](../../media/block-user-icon.png)。

   > [!NOTE]
   > アカウントが既にブロックされている場合、上部に **[サインインはブロックされました]** と表示され、アイコンは **[このユーザーのブロックを解除する]** と表示されます。

4. **[このユーザーをブロックしますか?]** ウィンドウで、**[このユーザーのサインインをブロックする]** を選択し、**[変更の保存]** を選択します。

Azure AD PowerShell を使用してアカウントのサインインをブロックする方法 (同時に多数のアカウントをブロックする方法など) の詳細については、「[Office 365 PowerShell でユーザー アカウントをブロックする](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md)」を参照してください。

## <a name="add-the-shared-mailbox-to-outlook"></a>共有メールボックスを Outlook に追加する

お客様の職場で自動マッピングを有効にしている場合 (既定では、ほとんどのユーザーが有効にします)、共有メールボックスは、ユーザーが Outlook を閉じて再起動した後にユーザーの Outlook アプリに自動的に表示されます。 

自動マッピングはユーザーのメールボックスに設定されますが、共有メールボックスには設定されません。   つまり、セキュリティ グループを使用して、共有メールボックスへのアクセス権を持つユーザーを管理する場合、自動マッピングは機能しません。 そのため、自動マッピングが必要な場合は、明示的にアクセス許可を割り当てる必要があります。 自動マッピングは既定でオンになっています。 この機能をオフにする方法については、「[Outlook for Office 365 で共有メールボックスの自動マッピングを削除する方法](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox)」を参照してください。

Outlook の共有メールボックスの詳細については、次を参照してください。

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Outlook で共有メールボックスを開いて使用する</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">共有メールボックスを Outlook on the web に追加する</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook Mobile に共有メールボックスを追加する</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Outlook for Mac で共有フォルダーまたはメールボックスを開く</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">共有メールボックスにルールを追加する</a>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>モバイル デバイス (スマートフォンまたはタブレット) で共有メールボックスを使用する

モバイル デバイスでは、次の 2 つの方法で共有メールボックスにアクセスできます。
- 共有メールボックスを <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS アプリ</a>、または <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android モバイル アプリ</a>に追加する。 
    
    手順については、「<a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook Mobile に共有メールボックスを追加する</a>」を参照してください。

- ブラウザーを開き、サインインして、Outlook on the web に移動します。 Outlook on the web から、共有メールボックスにアクセスできます。

    手順については、「<a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">共有メールボックスを Outlook on the web に追加する</a>」を参照してください。
    
> [!NOTE]
> 共有メールボックスは Outlook for iOS アプリ、または Outlook for Android モバイル アプリにのみ追加できます。

## <a name="use-the-shared-calendar"></a>共有の予定表を使う

共有メールボックスを作成すると、共有予定表が自動的に作成されます。SharePoint の予定表と比較して、予定や他の人の居場所を把握するのに便利です。共有予定表は Outlook に統合され、SharePoint の予定表に比べてはるかに簡単に利用することができます。

1. Outlook アプリで予定表ビューに移動し、共有メールボックスを選択します。

2. 予定を入力すると、共有メールボックスのメンバー全員がその予定を表示できます。

3. 共有メールボックスのすべてのメンバーは、予定表での予定の作成、表示、および管理を、個人的な予定の場合と同様に行えます。 共有メールボックスのメンバーになっているすべてのユーザーは、共有の予定表に加えられた変更を確認できます。

## <a name="related-content"></a>関連コンテンツ

[共有メールボックスについて](about-shared-mailboxes.md) (記事)\
[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)\
[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)\
[共有メールボックスからライセンスを削除する](remove-license-from-shared-mailbox.md) (記事)\
[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)
