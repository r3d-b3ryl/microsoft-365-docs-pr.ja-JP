---
title: OneDrive ファイル ストレージと共有を設定する
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
- Adm_O365_Setup
- SPO_Content
ms.custom:
- VSBFY23
- IT_Networking
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- ODB150
- ODB160
ms.assetid: 7aa9cdc8-2245-4218-81ee-86fa7c35f1de
description: Microsoft 365 ストレージと Microsoft 365 ファイル共有に OneDrive とチーム サイトを使用する方法について説明します。
ms.openlocfilehash: 7e8a56b6ad1199ddc857919eb6b00f6ef2538d3b
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085687"
---
# <a name="set-up-file-storage-and-sharing-in-microsoft-365"></a>Microsoft 365 でファイル ストレージと共有を設定する

ビジネス向けにファイル ストレージと共有を設定する最適な方法の 1 つは、OneDrive とチーム サイトを一緒に使用することです。 これは、従業員数の少ない中小企業に最適です。

## <a name="watch-where-to-store-files-in-office-365"></a>ウォッチ: ファイルをOffice 365に格納する場所

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FTHX] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。

## <a name="microsoft-365-document-storage-and-management"></a>Microsoft 365 ドキュメントのストレージと管理

- OneDrive は個別に使用できるように設計されており、ファイルを時折共有します。

- チーム サイトは、ファイルの共有と共同作業を定期的に行う目的で設計されています。 チーム サイトは、複数のユーザーがファイルを所有し、共同作業を行う可能性がある共有所有権を持つファイルを格納するのに最適です。 チーム サイトを追加する Microsoft Team を作成します。 [詳細については、「Teams でチームを作成する」を参照してください](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b)。

OneDrive サイトとチーム サイトの両方で、自分と従業員にどこからでもアクセスできます。
  
![Microsoft 365 製品で OneDrive または Team サイトを使用する方法を示す図。](../../media/7493131e-665f-4dbd-9a60-f5612aea7e42.png)
  
OneDrive とチーム サイトを一緒に使用する場合に、各場所に格納する内容に関する推奨事項を次に示します。<br/>

  
|保存場所|目的は何ですか|保存するファイル|
|:-----|:-----|:-----|
|**OneDrive** |OneDrive にコンテンツを格納することは、コンピューターにファイルを格納するようなものです。他のユーザーが簡単にアクセスすることはできません。<br/> 詳細については、「[OneDrive for Businessとは」](https://support.microsoft.com/office/187f90af-056f-47c0-9656-cc0ddca7fdc2)を参照してください。 <br/> |他のチーム メンバーが定期的に共同作業を行ったり、アクセスしたりする必要がないビジネス ファイル。<br/> |
|**SharePoint チーム サイト** <br/> |コラボレーション。 Microsoft 365 グループを作成すると (たとえば、Microsoft 365 管理センター、Outlook、Microsoft Teamsでチームを作成するなど)、そのグループの SharePoint チーム サイトが作成されます。 同様に、SharePoint ホーム ページまたは新しい SharePoint 管理センターから新しい SharePoint チーム サイトを作成すると、Microsoft 365 グループも作成されます。 詳細については、「 [SharePoint チーム サイトとは」と「SharePoint](https://support.microsoft.com/office/75545757-36c3-46a7-beed-0aaa74f0401e) [Online でチーム サイトを作成する」](https://support.microsoft.com/office/ef10c1e7-15f3-42a3-98aa-b5972711777d)を参照してください。  <br/> |共有所有権を持つファイル。 組織内の作業単位ごとに個別のチーム サイトをお勧めします。 たとえば、人員と財務ドキュメントを小規模なチームに非公開にするには、別のチーム サイトを作成します。  <br/> |

> [!NOTE]
> SharePoint には、ビジネスに使用できる他の種類のサイトもあります。 イントラネット内の [コミュニケーション サイト](https://support.microsoft.com/office/7fb44b20-a72f-4d2c-9173-fc8f59ba50eb) を使用して、幅広い対象ユーザーの情報を公開できます。 また、 [ハブ サイト](https://support.microsoft.com/office/fe26ae84-14b7-45b6-a6d1-948b3966427f) を使用してイントラネット内のサイトを接続できます。
  
## <a name="start-using-onedrive-and-your-team-site"></a>OneDrive とチーム サイトの使用を開始する

### <a name="team-members-can-store-their-own-files-in-onedrive"></a>チーム メンバーは、OneDrive に独自のファイルを格納できます

Microsoft 365 ライセンスが割り当てられている (および SharePoint Online が選択されている) ビジネス内の各ユーザーは、OneDrive クラウド ストレージを取得します。 ビジネス関連のファイルは、任意のデバイスからアクセスするためにここに保存でき、そのユーザーのみが使用できます。 たとえば、提案書の下書き、会議のメモ、配布予定のデモ用スクリプトなどを保存することができます。
  
従業員は、OneDrive のファイルとフォルダーを共有することもできます。 従業員が不在または退職した場合、他のユーザーは OneDrive (OneDrive チーム フォルダー共有) に格納されている共有ファイルにアクセスできます。
  
チームの各ユーザーが OneDrive を設定し、ファイルを共有する方法を次に示します。

1. <a href="https://admin.microsoft.com/ " target="_blank">Microsoft 365 管理センター</a>に移動し、ユーザー名とパスワードでサインインします。

2. アプリ起動ツールから **OneDrive** を選択します。

3. OneDrive では、チーム メンバーはビジネス関連の独自のファイルを格納できます。 個々のファイルまたはフォルダー全体を共有できます。 ファイルまたはフォルダーを選択し、右クリックして [ **共有**] を選択します。

    ![フォルダーの共有。](../../media/e8df9df3-aea5-404d-a320-92d7826c260c.png)
  
4. [ **リンクの送信** ] ページで、既定の選択 [ **リンクを持つすべてのユーザーが表示および編集できる**] のままにします。

    フォルダーにアクセスするチーム メンバーの名前または電子メール アドレスを入力し、オプションのメッセージを追加します。

    送信される電子メールの独自のコピーが必要な場合は、電子メール アドレスを一覧に追加します。

    ![名前の入力と選択を示すリンク ダイアログ ボックスを共有します。](../../media/877e6587-db9d-4903-a87b-11e570eee926.png)
  
5. 共有相手の入力が完了したら、[ **送信**] を選択します。 メールは、招待するユーザーに直ちに送信されます。

    ![名前の一覧を示すリンクを共有します。](../../media/e85625ea-7655-43f3-8623-72db68d0ea39.png)
  
6. 電子メールの外観を次に示します。 

    ![OneDrive フォルダーを共有するためのリンクをEmailします。](../../media/750c92e1-f14f-404c-a6a3-2095e26c680c.png)
  
### <a name="upload-files-to-a-team-site-for-online-collaboration"></a>オンライン コラボレーションのためにチーム サイトにファイルをアップロードする

チーム サイトには、ドキュメント ライブラリと呼ばれるファイルを格納する場所が用意されています。  
  
ファイルを追加する手順を次に示します。
  
1. チーム サイトのホーム ページで、左側のナビゲーション メニューから **[ドキュメント** ] を選択します。 これで、[ **ドキュメント ライブラリ**] が表示されます。
  
2. Microsoft 365 にサインインしている間は、タスク バーやその他の場所から Windows **エクスプローラー** を開きます。 チーム サイトにアップロードするファイルを表示します。

3. チーム サイトにアップロードするファイルを選択し、 **ドキュメント ライブラリ** にドラッグします。
  
4. 完了すると、ファイルはチーム サイトとコンピューターの両方に保存されます。
  
5. ファイルをコンピューターから削除することができます。 次の手順では、 [オンライン ファイルを PC または Mac と同期](#sync-online-files-with-your-pc-or-mac)して、コンピューター上にこれらのファイルの新しい場所を作成します。

    チーム サイトにアップロードするファイルや大きなファイルが多数ある場合は、 [ライブラリへの大きなファイルまたは多数のファイルのアップロードに関する](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)これらのヒントを参照してください。

    記憶域を追加する必要がある場合は、「[サブスクリプションの記憶域を変更する](../../commerce/add-storage-space.md)」を参照してください。

### <a name="sync-online-files-with-your-pc-or-mac"></a>オンライン ファイルを PC または Mac と同期する

ファイルをチーム サイトに保存したので、PC または Mac と同期するように設定することができます。 これにより、Microsoft Edge、Chrome、または別のブラウザーで作業する代わりに、PC または Mac からファイルを操作できます。 また、ファイルにアクセスする必要があるが、インターネットに接続していない場合に、同期済みのファイルがコンピューターに保存されていれば便利です。
  
コンピューターと同期するようにファイルを設定すると、インターネットに接続すると、自動的に同期されます。
  
次に、チーム サイトのファイルをデスクトップと同期する方法を示します。
  
1. チーム サイトのホーム ページで、左側のナビゲーション メニューから **[ドキュメント** ] を選択します。 これにより、ドキュメント ライブラリに移動します。

    > [!TIP]
    > チーム サイト上のファイルを同期するときは、サイト全体ではなく、サイト上の各ファイル ライブラリを同期します。
  
2. [ **同期]** を選択して、すべてのファイルを同期します。 または、同期する特定のフォルダーを参照します。

3. アプリの切り替えを求められた場合は、[ **はい**] を選択します。 OneDrive は、同期を実行するプロセスです。
  
4. その後、 **OneDrive のセットアップ** プロンプトが表示された場合は、職場または学校のアカウントでサインインします。

    ![OneDrive セットアップ画面。](../../media/82cbb1ac-2ac5-42bd-82de-ba710bf46145.png)
  
5. OneDrive をまだ同期していない場合は、[ **This is your OneDrive フォルダー** ] 画面が表示される場合があります。 OneDrive フォルダーの下のパス **がここにある** かどうかを確認します。 別のパスを使用する場合は、[ **場所の変更** ] を選択し、[ **次へ**] を選択します。

    ![この画面でローカル フォルダーを変更します。](../../media/6395485a-e729-4a9a-8e7d-b35e662435da.png)
  
6. チーム サイト内のファイルは、組織の名前の下にエクスプローラーの左側のウィンドウに表示されます。 OneDrive 内のファイルは、"OneDrive - \<Name of Organization\>" の下に表示されます

    ![ローカル フォルダーの同期内容を確認します。](../../media/93e2ca9f-4b5b-4930-a94d-ebc5b95aca84.png)
  
7. コンピューター上のチームのフォルダー内のファイルを開いて同期をテストします。 変更を加え、[保存] を選択 **します**。

## <a name="best-practices-for-file-storage-and-sharing"></a>ファイル ストレージと共有のベスト プラクティス

OneDrive または SharePoint チーム サイトから最大限に活用するためのヒントをいくつか紹介します。
  
### <a name="file-storage-and-collaboration-recommendations-for-other-types-of-small-businesses"></a>他の種類の中小企業のためのファイルの保存と共同作業に関する推奨事項

- **個人所有者**: OneDrive を使用して独自のファイルを保存し、ケースバイケースで顧客と共有します。

- **共同所有権**: 両方の所有者が OneDrive を使用し、ファイルを前後に共有します。

- **ファイルにアクセスする必要がある外部クライアントまたはパートナーを持つ企業**: 特定の顧客向けのドキュメントを保存して共有する新しいチーム サイトを作成します。 その顧客のみにアクセスできるようにサイトを設定します。 その後、ある顧客が別の顧客向けの情報に誤ってアクセスすることを心配する必要はありません。

### <a name="keep-private-files-private"></a>個人ファイルを非公開にする

OneDrive にファイルを格納する場合は、他のユーザーと共有しない限り、自分だけがアクセスできます。 ファイルを共有するときは、転送できるリンクを作成するか、特定のユーザーとのみ共有するかを選択できます。 また、公開用、個人用、個別のプロジェクト用など、さまざまな目的に合わせて OneDrive 内で各フォルダーを作成できます。 各フォルダーは、異なるユーザーやグループと共有したり、あるいは、誰とも共有しないように設定することもできます。
  
共有の詳細については、「 [Microsoft 365 でファイルとフォルダーを共有](https://support.microsoft.com/office/72f26d6c-bf9e-432c-8b96-e3c2437f5b65)する」も参照してください。
  
### <a name="track-how-much-space-you-have-left"></a>残っている容量を追跡する

OneDrive に残っているストレージ領域の量については、「[OneDrive for Business ストレージの管理](https://support.microsoft.com/office/31519161-059C-4764-B6F8-F5CD29F7FE68)」を参照してください。
  
### <a name="what-files-can-be-stored-in-onedrive-and-a-team-site"></a>OneDrive とチーム サイトに保存できるファイルは何ですか?

ほぼすべての種類のファイルをアップロードできますが、一部のファイル名とファイル名内の文字は許可されません。 詳細については、「[OneDrive for Businessの無効なファイル文字とファイルの種類](https://support.microsoft.com/office/64883A5D-228E-48F5-B3D2-EB39E07630FA)」を参照してください。
  
### <a name="enable-or-disable-third-party-storage-services"></a>サード パーティ製ストレージ サービスを有効または無効にする

Microsoft 365 のユーザーが OneDrive やチーム サイトに加えて Dropbox などのサービスを使用してドキュメントを保存および共有できるように、ユーザーのサード パーティストレージを有効にすることができます。 これは、ユーザーが既に使用しているか、ビジネス プロジェクトで使用することを好むサービスを提供する優れた方法です。 Office を使用している組織内のユーザーがサード パーティのサービスでファイルを開くのを望まない場合は、次の手順に従って無効にします。
  
> [!IMPORTANT]
> サード パーティ製ストレージは既定で有効になっているので、ユーザーが使用できないようにするには、すぐにこれらの手順を実行する必要があります。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にサインインします。

2. **[設定** 組織の設定] \> ページに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**します**</a>。

3. [**サービス**] タブで、**Office on the web** を選択します。

4. チェック ボックスをオンまたはオフにしてサード パーティのストレージをオンまたはオフにし、[ **変更の保存]** を選択します。

## <a name="next-steps"></a>次の手順

- [ファイルの保存と共有のためにチーム サイトをカスタマイズします](customize-team-site.md)。 このチュートリアルでは、ストレージとコラボレーションの機能をさらに活用する方法について説明します。

- **タブレットとスマートフォンで Office アプリをセットアップします。** OneDrive とチーム サイトに保存されているファイルをタブレットまたはスマートフォンから **編集** できるように、これを行う必要があります。 タブレットまたはスマートフォン用の Office アプリをインストールしない場合は、ファイルを表示できますが、編集することはできません。

  - [Microsoft 365 を使用して Android に Office をインストールしてセットアップする](https://support.microsoft.com/office/cafe9d6f-8b0c-4b03-b20a-12438a82a22d)

  - [Microsoft 365 を使用して iPhone または iPad に Office をインストールして設定する](https://support.microsoft.com/office/9df6d10c-7281-4671-8666-6ca8e339b628)

  - [Microsoft 365 を使用して office on Windows Phoneを設定する](https://support.microsoft.com/office/2b7c1b51-a717-45d6-90c9-ee1c1c5ee0b7)

## <a name="related-content"></a>関連コンテンツ

[サブスクリプションのストレージ領域を追加する](../../commerce/add-storage-space.md) (記事)\
[Microsoft 365 Business でファイルとフォルダーを共有](https://support.microsoft.com/office/share-files-and-folders-with-microsoft-365-business-72f26d6c-bf9e-432c-8b96-e3c2437f5b65) する (ビデオ)\
[ファイルの保存と共有用にチーム サイトをカスタマイズ](customize-team-site.md) する (記事)
