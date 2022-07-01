---
title: Google ワークスペースからビジネス用メールと予定表を移行する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: メール、連絡先、予定表を Google ワークスペースから Microsoft 365 for Business に移行する方法について説明します。
ms.openlocfilehash: be7637816f80ecba3c56db644114d5ddb00caeb7
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602040"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Google ワークスペースからビジネス用メールと予定表を移行する

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

## <a name="watch-migrate-business-email-and-calendar-from-google-workspace"></a>ウォッチ: Google ワークスペースからビジネス用メールと予定表を移行する

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198034)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

管理者が実行した移行を使用して、Google ワークスペースからExchange Onlineできます。 メールは、一度に移行することも、段階的に移行することもできます。 次の手順では、電子メール データを一度に移行する方法を示します。 詳細については、「 [G Suite の移行を実行する](/exchange/mailbox-migration/perform-g-suite-migration)」を参照してください。

移行プロセスにはいくつかの手順が必要であり、移行するデータの量に応じて数時間から数日かかる場合があります。

### <a name="create-a-google-service-account"></a>Google サービス アカウントを作成する

1. Chrome ブラウザーを使用して、admin.google.com で Google ワークスペース管理コンソールにサインイン [します](https://admin.google.com)。 
1. 新しいタブまたはウィンドウで、[ [サービス アカウント](https://console.developers.google.com/iam-admin/serviceaccounts) ] ページに移動します。 
1. [ **プロジェクトの作成]** を選択し、プロジェクトに名前を付け、[作成] を選択 **します**。 
1. [ **サービス アカウントの作成**] を選択し、名前を入力して[ **作成** ]、[ **完了]** の順に選択します。 
1. **[アクション]** メニューを開き、[**編集]** を選択して、[一意の ID] をメモします。 この ID は、プロセスの後半で必要になります。 
1. **[ドメイン全体の委任の表示**] セクションを開きます。 
1. [ **G Suite ドメイン全体の委任を有効にする]** を選択し、同意画面の製品名を入力して、[ **保存]** を選択します。 

    > [!NOTE]
    > 製品名は移行プロセスでは使用されませんが、ダイアログに保存するために必要です。     

1. [ **アクション]** メニューをもう一度開き、[ **キーの作成**] を選択します。 
1. **[JSON**]、[**作成**] の順に選択します。 

     秘密キーは、デバイス上のダウンロード フォルダーに保存されます。
 
1. **[閉じる]** を選択します。 

### <a name="enable-api-usage-for-the-project"></a>プロジェクトの API の使用を有効にする

1. [[API] ページ](https://console.developers.google.com/apis/library)に移動します。 
1. 検索バーに **「Gmail API」と入力します**。
1. それを選択し、[ **有効]** を選択します。
1. Google Calendar API、People API、Contacts API に対してこのプロセスを繰り返します。 

### <a name="grant-access-to-the-service-account"></a>サービス アカウントへのアクセスを許可する

1. Google ワークスペース管理コンソールに戻ります。 
1. [ **セキュリティ**] を選択し、下にスクロールして **API コントロールを開きます**。 
1. 下にスクロールし、[ **ドメイン全体の委任の管理**] を選択します。
1. [ **新規追加]** を選択し、前にメモしたクライアント ID を入力します。
1. 次に、Google API の OAuth スコープを入力します。 これらは、手順 5 の [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) で使用できます。

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. [ **承認] を選択します**。 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Microsoft 365 に送信するメールのサブドメインを作成する

1. **Google ワークスペース管理** コンソールに戻ります。
1. **[ドメイン]**、[**ドメインの管理**]、[**ドメイン エイリアスの追加]** の順に選択します。 
1. 次のような `m365.contoso.com`ドメイン エイリアスを入力します。
1. 次に、[続行] を選択 **し、ドメインの所有権を確認** します。 

    ドメインの検証には通常数分かかりますが、最大で 48 時間かかる場合があります。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. Microsoft 365 管理センターの左側のナビゲーションで、[**すべての** > 設定 <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**ドメイン**</a>の表示 **]** >  を選択し、[**ドメインの追加]** を選択します。 
1. 前に作成したサブドメインを入力し、[ **このドメインを使用** する] を選択します。 
1. ドメインに接続するには、[続行] を選択 **します**。 
1. 下にスクロールして、MX レコード、CNAME レコード、TXT レコードをメモします。 
1. **Google 管理コンソール** に戻ります。
1. **[ドメイン]** を選択し、[**ドメインの管理**]、[**詳細の確認**] の順に選択して、[**ドメインの管理] を選択します**。 
1. 左側のナビゲーションで [ **DNS** ] を選択し、[ **カスタム リソース レコード]** まで下にスクロールします。 
1. レコードの種類ドロップダウンを開き、[ **MX**] を選択し、前に入力した MX レコード情報を入力またはコピーして貼り付けて、[ **追加**] を選択します。 
1. CNAME レコードと TXT レコードに対してプロセスを繰り返します。 

    これらの変更が有効になるには時間がかかる場合があります。  

1. Microsoft 365 管理センターで中断した場所に戻り、[続行] を選択 **します**。 

これで、ドメインが設定されました。  

### <a name="create-email-aliases-in-microsoft-365"></a>Microsoft 365 で電子メール エイリアスを作成する

移行を開始する前に、新しいサブドメインを持つユーザーの電子メール エイリアスを作成する必要があります。 

1. 次の手順を開始するには、Microsoft 365 管理センターの **[ドメインの追加**] ウィザードで [**アクティブなユーザーに移動**] を選択します。 
1. ユーザーを選択し、ユーザー **名と電子メールを管理** します。 
1. **[ドメイン**] ドロップダウンから、以前に作成したサブドメインを選択します。 
1. ユーザー名を入力し、[ **追加]**、[ **変更の保存]** の順に選択し、ウィンドウを閉じます。 

    ユーザーごとにこのプロセスを繰り返します。 

### <a name="start-the-migration-process"></a>移行プロセスを開始する

完了したら、移行する準備が整いました。 

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>の左側のナビゲーションで、**管理センター** まで下にスクロールし、**Exchange** を選択します。 
1. **受信者の** 下で[**移行**] を選択し、[**新規**]、[**Exchange Onlineへの移行**] の順に選択し、[**G Suite の移行**] を選択して、[**次へ**] を選択します。 
1. 移行するメールボックスの一覧を含む CSV ファイルを作成します。 ファイルがこの形式に従っていることを確認します。 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      詳細については、「 [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)」を参照してください。 

1. [ **ファイルの選択] を選択** し、CSV ファイルに移動して選択し、[ **開く**]、[ **次へ**] の順に選択します。 
1. テストに使用する管理者のメール アドレスを確認します。 
1. [ **ファイルの選択] を選択** し、前に作成した JSON ファイル (通常はコンピューターの [ダウンロード] フォルダー) に移動し、それを選択して **[開く**]、[ **次へ**] の順に選択します。 
1. **[新しい移行バッチ** 名] フィールドに名前を入力します。
1. **[ターゲット配信ドメイン**] フィールドに作成したサブドメインを入力し、[**次へ**]、[**新規**] の順に選択します。 
1. 情報が保存されたら、[OK] を選択 **します**。 

    移行の状態を表示できるようになりました。 

1. 移行するユーザーの数に応じて、しばらく時間が経過したら、[更新] を選択 **します**。 
1. 状態が **[同期済み**] に変更されたら、[ **この移行バッチを完了** する]、[ **はい**] の順に選択します。 
1. プロセスが完了すると、状態は **[完了]** に変わります。 
1. 必要に応じて、[詳細の **表示** ] を選択して移行の詳細を確認できます。 
1. **[閉じる]** を選択します。 
1. Outlook を開き、Google ワークスペースからのすべてのメールが正常に移行されたことを確認します。
予定表アイテムと連絡先についても、これを繰り返すことができます。
