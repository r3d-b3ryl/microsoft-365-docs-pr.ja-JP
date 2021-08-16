---
title: Google ワークスペースからビジネス メールと予定表を移行する
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: メール、連絡先、予定表を Google ワークスペースからビジネス向けMicrosoft 365する方法について説明します。
ms.openlocfilehash: 26ed00be3241f07d564fd7823c44610cf34d6ffd96cc4becb36d907439f23629
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53896561"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Google ワークスペースからビジネス メールと予定表を移行する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

管理者が実行した移行を使用して、Google ワークスペースExchange Online移行できます。 メールは、一度に、または段階で移行できます。 次の手順は、電子メール データを一度に移行する方法を示しています。 詳細については [、「G Suite 移行の実行」を参照してください](/exchange/mailbox-migration/perform-g-suite-migration)。

移行プロセスにはいくつかの手順が必要で、移行するデータの量に応じて数時間から数日かかる場合があります。

## <a name="try-it"></a>お試しください!

### <a name="create-a-google-service-account"></a>Google サービス アカウントを作成する

1. Chrome ブラウザーを使用して、Google Workspace 管理コンソールにサインインします[(admin.google.com)。](https://admin.google.com) 
1. 新しいタブまたはウィンドウで、[サービス アカウント] [ページに移動](https://console.developers.google.com/iam-admin/serviceaccounts) します。 
1. [プロジェクト **の作成] を** 選択し、プロジェクトに名前を付け、[作成] を **選択します**。 
1. [サービス **アカウントの作成] を** 選択し、名前を入力し、[作成] **と [完了** ] の順に **選択します**。 
1. [アクション] **メニューを** 開き、[編集] **を** 選択し、一意の ID をメモします。 この ID は、プロセスの後半で必要になります。 
1. [ドメイン全体 **の委任を表示する] セクションを開** きます。 
1. [G **Suite ドメイン全体の委任を有効にする**] を選択し、同意画面の製品名を入力し、[保存] を **選択します**。 

    > [!NOTE]
> 製品名は移行プロセスでは使用されませんが、ダイアログに保存するために必要です。     

1. [操作] **メニューを再度** 開き、[キーの作成 **] を選択します**。 
1. **[JSON] を選択** し、[作成 **] を選択します**。 

     プライベート キーは、デバイスのダウンロード フォルダーに保存されます。
 
1. **[閉じる]** を選択します。 

### <a name="enable-api-usage-for-the-project"></a>プロジェクトの API 使用法を有効にする

1. [[API] ページに移動します](https://console.developers.google.com/apis/library)。 
1. 検索バーに **「Gmail API」と入力します**。
1. それを選択し、[有効にする] **を選択します**。
1. Google カレンダー API と連絡先 API でこのプロセスを繰り返します。 

### <a name="grant-access-to-the-service-account"></a>サービス アカウントへのアクセスを許可する

1. Google Workspace 管理コンソールに戻ります。 
1. [セキュリティ **] を選択** し、下にスクロールして API コントロール **を開きます**。 
1. 下にスクロールして、[ **ドメイン全体の委任の管理] を選択します**。
1. [ **新規追加] を** 選択し、前にメモしたクライアント ID を入力します。
1. 次に、Google API の OAuth スコープを入力します。 これらは、手順 [5 の aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) で使用できます。

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. [ **承認] を選択します**。 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>メールを送信するサブドメインを作成Microsoft 365

1. Google Workspace 管理 **コンソールに戻** ります。
1. [**ドメイン] 、[****ドメインの管理]** の順に選択し、[**ドメイン エイリアスの追加] を選択します**。 
1. のようなドメイン エイリアスを入力します `m365.contoso.com` 。
1. 次に、[ **続行] を選択し、ドメインの所有権を確認します**。 

    通常、ドメイン検証には数分かかりますが、最大 48 時間かかる場合があります。

1. 
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。
1. [ドメイン] **Microsoft 365 管理センター** 左側のナビゲーションで、[すべて表示] 、[ドメイン] 、[**ドメイン設定] の順** に選択し、[ドメインの追加]**を選択します**。  
1. 以前に作成したサブドメインを入力し、[このドメインを使用 **する] を選択します**。 
1. ドメインを接続するには、[続行] を **選択します**。 
1. 下にスクロールして、MX レコード、CNAME レコード、および TXT レコードをメモします。 
1. Google 管理コンソール **に戻る**。
1. [ **ドメイン] を選択し**、[ **ドメインの管理]**、[ **詳細の確認** ] の順に選択し、[ドメインの管理] **を選択します**。 
1. 左側のナビゲーションで **、[DNS] を選択し** 、[カスタム リソース レコード **] まで下にスクロールします**。 
1. [レコードの種類] ドロップダウンを開き **、[MX]** を選択し、以前に記録した MX レコード情報を入力またはコピーして貼り付け、[追加] を **選択します**。 
1. CNAME レコードと TXT レコードの処理を繰り返します。 

    これらの変更を有効にするには、時間がかかる場合があります。  

1. [次へ] でオフにした場所Microsoft 365 管理センターし **、[** 続行] を **選択します**。 

これで、ドメインがセットアップされます。  

### <a name="create-email-aliases-in-microsoft-365"></a>メール エイリアスを作成Microsoft 365

移行を開始する前に、新しいサブドメインを使用してユーザーのメール エイリアスを作成する必要があります。 

1. 次の手順を開始するには、ドメインの追加ウィザードの [ドメインの追加] Microsoft 365 管理センター [アクティブ ユーザーに移動]**を選択します**。 
1. ユーザーを選択し、[ユーザー名と **メールの管理] を選択します**。 
1. [ドメイン **] ドロップダウンから** 、以前に作成したサブドメインを選択します。 
1. ユーザー名を入力し、[追加] **、[変更の****保存]** を選択し、ウィンドウを閉じます。 

    ユーザーごとにこのプロセスを繰り返します。 

### <a name="start-the-migration-process"></a>移行プロセスを開始する

完了したら、移行する準備ができました。 

1. [管理センター] の左側の **ナビゲーションMicrosoft 365 管理センター[** 管理センター]まで下にスクロールし、[**管理センター]** をExchange。 
1. [**受信者] で、[** 移行] **を** 選択し、[新規] 、[移行Exchange Online、[ **G Suite** の移行] の順に選択し **、[次** へ] を **選択します**。 
1. 移行するメールボックスの一覧を含む CSV ファイルを作成します。 ファイルが次の形式に従う必要があります。 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      詳細については、「aka.ms/GoogleWorkspaceMigration」 [を参照してください](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)。 

1. [ **ファイルの選択]** を選択し、CSV ファイルに移動して選択し、[開く] 、[ **次** へ] の順に **選択します**。 
1. テストに使用する管理者メール アドレスを確認します。 
1. [**ファイルの選択]** を選択し、前に作成した JSON ファイル (通常はコンピューターの [ダウンロード] フォルダー) に移動し、それを選択し、[開く] 、[次へ] の **順に****選択します**。 
1. [新しい移行バッチ名 **] フィールドに名前を入力します**。
1. [ターゲット配信ドメイン] フィールドに作成したサブドメイン **を入力** し、[次へ] を選択し、[新規] を **選択します**。 
1. 情報を保存したら **、[OK] を選択します**。 

    これで、移行の状態を表示できます。 

1. 移行するユーザーの数に応じて、しばらく時間が経過した後、[更新] を **選択します**。 
1. 状態が [同期済み] に **変更したら**、[この移行 **バッチを完了する**] を選択し、[はい] を **選択します**。 
1. プロセスが完了すると、状態は [完了] に **変わります**。 
1. 必要な場合は、[詳細の表示] **を選択して** 、移行の詳細を確認できます。 
1. **[閉じる]** を選択します。 
1. [Outlookを開き、Google Workspace からのすべてのメールが正常に移行されたことを確認します。
予定表アイテムと連絡先にもこの操作を繰り返します。