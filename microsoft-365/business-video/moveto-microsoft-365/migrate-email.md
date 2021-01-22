---
title: Google Workspace からビジネス メールとカレンダーを移行する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google Workspace からビジネス向け Microsoft 365 にメール、連絡先、予定表を移行する方法について説明します。
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928248"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Google Workspace からビジネス メールとカレンダーを移行する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Google Workspace から Exchange Online への管理者が実行した移行を使用できます。 メールは、一度に移行するか、または段階で移行できます。 次の手順は、メール データを一度に移行する方法を示しています。 詳細については [、「G Suite の移行を実行する」を参照してください](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)。

移行プロセスはいくつかの手順を実行し、移行するデータの量に応じて数時間から数日かかる場合があります。

## <a name="try-it"></a>演習

### <a name="create-a-google-service-account"></a>Google サービス アカウントを作成する

1. Chrome ブラウザーを使用して、Google Workspace 管理コンソールにサインイン[admin.google.com。](https://admin.google.com) 
1. 新しいタブまたはウィンドウで、[サービス アカウント] [ページに移動](https://console.developers.google.com/iam-admin/serviceaccounts) します。 
1. [プロジェクト **の作成] を選択し**、プロジェクトに名前を付け、[作成] を **選択します**。 
1. Select **Create service account,** enter a name, choose **Create** and then **Done**. 
1. [操作] **メニューを** 開き、[編集] **を選択して**、一意の ID をメモします。 この ID は、プロセスの後半で必要になります。 
1. [ドメイン全体 **の委任の表示] セクションを開** きます。 
1. [G **Suite ドメイン全体の委任を有効** にする] を選択し、同意画面の製品名を入力して、[保存] を **選択します**。 

    > [!NOTE]
> 製品名は移行プロセスでは使用されませんが、ダイアログに保存する必要があります。     

1. もう一度 **[操作] メニュー** を開き、[キーの **作成] を選択します**。 
1. **[JSON] を選択** し、[作成 **] を選択します**。 

     このプライベート キーは、デバイスのダウンロード フォルダーに保存されます。
 
1. **[閉じる]** を選択します。 

### <a name="enable-api-usage-for-the-project"></a>プロジェクトの API の使用を有効にする

1. API ページ [に移動します](https://console.developers.google.com/apis/library)。 
1. 検索バーに **「Gmail API」と入力します**。
1. それを選択し、[有効にする] を **選択します**。
1. Google カレンダー API と連絡先 API に対してこのプロセスを繰り返します。 

### <a name="grant-access-to-the-service-account"></a>サービス アカウントへのアクセスを許可する

1. Google Workspace 管理コンソールに戻ります。 
1. [ **セキュリティ] を選択** し、下にスクロールして API コントロール **を開きます**。 
1. 下にスクロールして、[ **ドメイン全体の委任の管理] を選択します**。
1. [新規 **追加]** を選択し、前にメモしたクライアント ID を入力します。
1. 次に、Google API の OAuth スコープを入力します。 これらは手順 5 の [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) で利用できます。

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Choose **Authorize**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Microsoft 365 に送信されるメールのサブドメインを作成する

1. Google Workspace 管理 **コンソールに戻** ります。
1. Select **Domains,** **Manage domains,** then, **Add a domain alias**. 
1. 次のようなドメイン エイリアスを入力します `m365.contoso.com` 。
1. 次に、[ **続行] を選択し、ドメインの所有権を確認します**。 

    通常、ドメインの検証には数分かかりますが、最大 48 時間かかる場合があります。

1. 
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. Microsoft **365** 管理センターの左側のナビゲーションで、[すべて表示] 、[**設定**] 、[ドメイン] の順に選択し、[ドメインの追加]**を選択します**。  
1. 以前に作成したサブドメインを入力し、[このドメインを使用 **する] を選択します**。 
1. ドメインを接続するには、[続行] を **選択します**。 
1. 下にスクロールして、MX レコード、CNAME レコード、および TXT レコードをメモします。 
1. Google 管理コンソール **に戻る**。
1. Select **Domains,** select **Manage domains,** **Verify Details** and then, Manage **domain**. 
1. 左側のナビゲーションで **、[DNS]** を選択し、[カスタム リソース レコード] **まで下にスクロールします**。 
1. Open the record type dropdown and select **MX,** enter or copy and paste the MX record information you previously noted, then choose **Add**. 
1. CNAME レコードと TXT レコードに対してこのプロセスを繰り返します。 

    これらの変更が有効にな時期が近付く場合があります。  

1. **Microsoft 365** 管理センターでオフにした場所に戻り、[続行] を選択 **します**。 

これで、ドメインがセットアップされます。  

### <a name="create-email-aliases-in-microsoft-365"></a>Microsoft 365 でメール エイリアスを作成する

移行を開始する前に、新しいサブドメインを使用してユーザーの電子メール エイリアスを作成する必要があります。 

1. 次の手順を開始するには、Microsoft  365 管理センターのドメインの追加ウィザードで、[アクティブなユーザーに移動]**を選択します**。 
1. ユーザーを選択し、ユーザー名と **メールを管理します**。 
1. **[Domains] ドロップダウン** から、前に作成したサブドメインを選択します。 
1. ユーザー名を入力し、[追加] **を選択し**、[ **変更の保存] を** 選択して、ウィンドウを閉じます。 

    ユーザーごとにこのプロセスを繰り返します。 

### <a name="start-the-migration-process"></a>移行プロセスを開始する

完了したら、移行の準備が整いました。 

1. **Microsoft 365** 管理センターの左側のナビゲーションで、[管理センター ] まで下にスクロールし **、[Exchange]** を選択します。 
1. [**受信者] で、[****移行**]を選択し、[新規]、[Exchange Online に移行 **]、G** **Suite** の移行、[次へ] の順に **選択します**。 
1. 移行するメールボックスの一覧を含む CSV ファイルを作成します。 ファイルが次の形式に従う必要があります。 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      詳細については、以下を[参照aka.ms/GoogleWorkspaceMigration。](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac) 

1. Select **Choose File,** navigate to the CSV file, choose it, select **Open,** then **Next**. 
1. テストに使用する管理者のメール アドレスを確認します。 
1. Select **Choose File,** navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open,** then **Next**. 
1. [新しい移行バッチ名 **] フィールドに名前を入力します**。
1. [ターゲット配信ドメイン] フィールドに作成したサブドメイン **を** 入力し、[次へ] を選択し、[新規] を **選択します**。 
1. 情報を保存したら **、[OK]** を選択します。 

    これで、移行の状態を表示できます。 

1. 移行するユーザーの数に応じて、しばらく時間が経過した後、[最新の情報に更新] を選択 **します**。 
1. 状態が [同期済み] に変わったら、[この移行バッチを完了する] を選択し **、[** はい] を **選択します**。 
1. プロセスが完了すると、状態が [完了] に **変わります**。 
1. 必要に合う場合は、[詳細の表示 **] を** 選択して、移行の詳細を確認できます。 
1. **[閉じる]** を選択します。 
1. Outlook を開き、Google Workspace からのすべてのメールが正常に移行されたことを確認します。
予定表アイテムと連絡先に対して、この操作を繰り返し行います。