---
title: データを Microsoft 365 Business Standard サブスクリプションに移行する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
description: Outlook、OneDrive、Teams のデータをMicrosoft 365 Business Standardに移行する
ms.openlocfilehash: 2bb4b401266b61832c5d9ae2fcd8dd45314b4418
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085095"
---
# <a name="migrate-data-to-my-microsoft-365-business-standard-subscription"></a>データを Microsoft 365 Business Standard サブスクリプションに移行する

この記事の手順に従って、OneDrive、Outlook、Teams のデータをMicrosoft 365 Business Standard サブスクリプションに移動します。

> [!IMPORTANT]
> 個人アカウントにデータを保持することはできます。 新しいビジネス用メール アカウントを作成してデータを移行しても、個人アカウントのデータの有効期限は切れません。 すべてのデータを新しいビジネス アカウントに移動することも、一部のデータを移動することもできます。 たとえば、職場のドキュメントをビジネス アカウントに移動できますが、個人の家族の写真は個人用アカウントに保持できます。

## <a name="move-files-to-onedrive-for-business"></a>OneDrive for Business にファイルを移動する

このセクションでは、Microsoft 365 個人アカウントに格納されているファイルを Microsoft 365 ビジネス アカウントに移動する方法について説明します。 両方の OneDrive アカウントをデバイスに同期すると、2 つの OneDrive フォルダー間でファイルを簡単にドラッグ アンド ドロップできます。

1. Windows 通知領域で OneDrive の白いクラウド アイコンを選択し、OneDrive 個人用アカウントがデバイスと同期されていることを確認します。

    :::image type="content" source="../../media/ssu-onedrive-icons.png" alt-text="スクリーンショット: Windows 通知領域で白いクラウド アイコンを選択する":::

    > [!NOTE]
    > OneDrive アイコンを表示するには、通知領域の横にある **[非表示のアイコンの表示** ] 矢印を選択することが必要な場合があります。 通知領域にアイコンが表示されない場合は、OneDrive が実行されていない可能性があります。 **[スタート] を** 選択し、検索ボックスに「OneDrive」と入力し、検索結果で OneDrive を選択します。

2. 新しいビジネス アカウントを追加するには、[**ヘルプ &設定]** >  を選択 **します**。

    :::image type="content" source="../../media/ssu-onedrive-help-settings.png" alt-text="スクリーンショット: [ヘルプ &設定] を選択してアカウントを追加する":::

3. **[設定]** で、[**アカウントの** > 追加] を選択 **します**。

4. OneDrive セットアップが開始されたら、新しいビジネス アカウントを入力し、[ **サインイン**] を選択します。

    :::image type="content" source="../../media/ssu-setup-onedrive.png" alt-text="スクリーンショット: OneDrive のセットアップ ページにメール アドレスを入力します":::

    > [!NOTE]
    > 以前に現在の Microsoft 365 個人用アカウントで OneDrive を設定していない場合は、上記の手順に従ってデバイスに個人用アカウントを設定し、ファイルを同期してから、次の手順に進みます。

### <a name="drag-and-drop-files-in-onedrive"></a>OneDrive でファイルをドラッグ アンド ドロップする

Microsoft 365 個人アカウントとビジネス アカウントの両方をデバイスに同期することで、ファイルを個人用 OneDrive フォルダーから新しいビジネス OneDrive フォルダーに移動できるようになりました。

1. エクスプローラーで、ファイルを含む同期済みの OneDrive フォルダーを開きます。

2. OneDrive 個人用フォルダーから目的のファイルを選択し、新しい OneDrive ビジネス フォルダーにドラッグします。

    :::image type="content" source="../../media/ssu-onedrive-files-to-work-folder.png" alt-text="スクリーンショット: 新しい OneDrive for Business フォルダーにファイルをドラッグ アンド ドロップする":::

### <a name="notes-about-moving-files-from-onedrive-personal-to-onedrive-for-work"></a>OneDrive personal から OneDrive へのファイルの移動に関する注意事項

- 多数のファイルを移動する場合は、それぞれ 100 個以下のファイルのバッチでファイルを移動することをお勧めします。

- 作業のために OneDrive 個人用から OneDrive に移動したファイルは新しいファイルとして認識され、その結果、これらのファイルは変更者や変更者などのメタデータの詳細を保持しません。

- 以前に OneDrive でファイルを共有した場合は、移動後に新しい OneDrive でこれらのファイルをもう一度共有する必要があります。 また、これらのファイルを共有したら、OneDrive から元のファイルを削除することをお勧めします。 これにより、ユーザーは以前に共有したファイルの古いコピーを参照できなくなります。

## <a name="step-set-up-outlook-for-email"></a>手順: Outlook をメール用にセットアップする

1. Windows の [スタート] メニューで、[Outlook] を検索し、選択します。

    (Mac を使用している場合は、ツールバーから Outlook を開くか、または Finder を使用して Outlook を検索します)。

    Outlook をインストールしたばかりの場合は、[ようこそ] ページで、[**次へ**] を選択します。

2. [**ファイル**] \> [**情報**] \> [**アカウントの追加**] の順に選択します。

3. Microsoft のメール アドレスを入力して、**[接続]** を選択します。

## <a name="watch-set-up-outlook-for-email"></a>注目 : Outlook を電子メール用にセットアップして下さい。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
詳細については、「[メール用に Outlook をセットアップする](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f)」を参照してください。
  
### <a name="import-email"></a>メールをインポートする

別のメール アカウントで Outlook を使用していた場合は、以前のメール、予定表、連絡先を新しい Microsoft アカウントにインポートできます。
  
1. **古いメールをエクスポートする**

    Outlook で、[**ファイル**] \> [**開く&amp;エクスポート**] \> [**インポート/エクスポート**] の順に選択します。

    [**ファイルにエクスポート**] を選択し、手順に従って Outlook データ ファイル (.pst) およびすべてのサブフォルダーをエクスポートします。

2. **古いメールをインポートする**

    Outlook で、[**ファイル**] \> [**開く&amp;エクスポート**] \> [**インポート/エクスポート**] を再度選択します。

    今度は、[**他のプログラムまたはファイルからのインポート**] を選択し、古いメールをエクスポートしたときに作成したバックアップ ファイルを手順に従ってインポートします。

### <a name="watch-import-and-redirect-email"></a>注目 : 電子メールをインポートして再配置しましょう。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
詳細については、「[Outlook でメールをインポートする](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de)」を参照してください。

また、Exchange 管理センターを使用して、すべてのユーザーのメールをインポートすることもできます。 詳細については、「[複数のメール アカウントを移行する](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。

## <a name="move-data-from-your-personal-microsoft-teams-account-to-new-teams-for-work-account"></a>個人用Microsoft Teams アカウントから仕事用アカウントの新しい Teams にデータを移動する

1. Microsoft Teams を開き、プロファイル アイコンを選択して、**[職場または学校アカウントを追加する]** を選択します。

2. 手順に従って、新しいアカウントを Teams に追加します。 詳細については、 [サインインを確認し、Teams](https://support.microsoft.com/office/sign-in-and-get-started-with-teams-6723dc43-dbc0-46e6-af49-8a2d1c5cb937) の使用を開始してください。

### <a name="access-teams-chats"></a>Teams チャットにアクセスする

新しい職場アカウントで Teams の使用を開始すると、データは移行されません。 古いチャットを表示する最善の方法は、古い Teams アカウントと新しい職場アカウントを並べて開く方法です。 これを行うには、Teams の右上にある ME アイコンを選択し、開くアカウントを選択します。 新しい職場アカウントで Teams の使用を同僚と開始できます。 チャット相手の他のユーザーに、新しい Teams for Work アカウントを使用して連絡を開始するように指示してください。

### <a name="microsoft-teams-meetings"></a>Microsoft Teams会議

仕事用の新しいMicrosoft Teams アカウントを設定したら、Teams 予定表で会議を再作成できます。 古い Teams アカウントの元の会議は必ず削除してください。 これにより、スケジュール設定時の予定表の可用性、会議を記録する機能など、より充実した機能にアクセスできます。 自分の Teams 予定表からのみ会議を削除できます。そのため、会議を持つユーザーに会議を再作成することを知らせます。 会議に新しい Teams アカウントを使用するように切り替える際に、会議に参加する必要があるユーザーが見つからない場合は、そのユーザーに連絡して、以前の会議リンクに参加していないことを確認します。

### <a name="migrating-contacts"></a>連絡先の移行

個人の Teams アカウントから連絡先を移行するには、連絡先のメール アドレスを見つけて、仕事用の新しい Teams アカウントにユーザーを追加します。

## <a name="related-content"></a>関連コンテンツ

[Gmail または別のメール プロバイダーから Microsoft 365 にメールをインポートまたは移行する](../setup/migrate-email-and-contacts-admin.md)

<!--## Download desktop apps

Download Microsoft 365 apps by following the steps in this article.

1. Open any of your Microsoft 365 apps, like Word, Excel or PowerPoint, select your profile icon and then **Sign in with a different account**. Follow the steps and choose **Next** to set up Outlook.

2. Open Outlook, enter your new email address, and select **Connect**. Follow the steps and choose **Next** to set up OneDrive.

3. Select the OneDrive cloud icon from your taskbar and follow the steps to move your files to your new OneDrive for Business folder. Select **Next** to set up Microsoft Teams.

4. Open Teams, select your profile icon, and then **Add work or school account**. Follow the steps to add your new account to Teams. Select **I'm done** when Teams is set up.-->

<!--## Next steps

## Accept a new invitation to change your personal email account to a business email account

Your email looks like this to set up your business user account. When you get this email, you'll have to complete a few steps before you can start using your new user account.

(**Add screenshot here**)

1. From the invitation email, select **Accept**.

2. On the **Join Microsoft 365 Business...** page, select **Next**.

3. On the Sign up page, make sure you use the email used in the invitation email, and create a password. Select **Create account**.

3. Choose **Accept** on the **Terms and Conditions** page.

1. On the Review permissions page, choose **Accept**.

1. On the Welcome to Microsoft 365 page, you can download Office desktop and mobile apps, and set up OneDrive.-->