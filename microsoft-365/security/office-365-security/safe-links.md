---
title: 安全なリンク
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: この記事では、管理者は、フィッシングや悪意のある URL を使用する他の攻撃から組織を保護するために、Office 365 の Defender のセーフ リンク保護について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ec3ab1a255e9eaa8c190ed5c248c9587273e03
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206560"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全なリンク

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlook.com、Microsoft 365 ファミリ、または Microsoft 365 Personal を使用している場合、Outlook で Safelinks に関する情報を探している場合は、「Advanced Outlook.com security 」 [を参照](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)してください。

セーフ リンクは、メール フロー内の受信メール メッセージの URL のスキャンと書き換え、および電子メール メッセージなどの URL とリンクのクリック時の検証を提供する [、Defender for Office 365](defender-for-office-365.md) の機能です。 安全なリンクのスキャンは、Exchange Online [](anti-spam-and-anti-malware-protection.md) Protection (EOP) の受信電子メール メッセージの通常のスパム対策およびマルウェア対策保護に加えて行われます。 安全なリンクスキャンは、フィッシングなどの攻撃で使用される悪意のあるリンクから組織を保護するのに役立ちます。

安全なリンク保護は、次の場所で利用できます。

- **電子メール メッセージ**: 電子メール メッセージ内のリンクに対するセーフ リンク保護は、セーフ リンク ポリシーによって制御されます。 既定のセーフ リンク ポリシーはないので、電子メール メッセージでセーフ リンクの保護を取得するには、1 つ以上のセーフ リンク ポリシーを **作成する必要があります**。 手順については [、「Set up Safe Links policies in Microsoft Defender for Office 365」を参照してください](set-up-safe-links-policies.md)。

  電子メール メッセージのセーフ リンク保護の詳細については、この記事の後半の「電子メール メッセージのセーフ リンク [設定」セクション](#safe-links-settings-for-email-messages) を参照してください。

- **Microsoft Teams** (現在 TAP プレビュー): Teams の会話、グループ チャット、またはチャネルからのリンクに対するセーフ リンク保護は、セーフ リンク ポリシーによっても制御されます。 既定のセーフ リンク ポリシーはないので、Teams でセーフ リンクの保護を取得するには、1 つ以上のセーフ リンク ポリシーを **作成する必要があります**。

  Teams のセーフ リンク保護の詳細については、この記事の後半の [「Microsoft Teams](#safe-links-settings-for-microsoft-teams) の安全なリンク設定」セクションを参照してください。

- **Office 365** アプリ : 365 アプリOfficeセーフ リンク保護は、サポートされているデスクトップ、モバイル、および Web aps で利用できます。 セーフ **リンク** ポリシーの外部にあるグローバルOffice 365 アプリに対してセーフ リンク保護を構成します。 手順については、「Configure global settings for Safe Links settings [in Microsoft Defender for microsoft Defender for Office 365」 を参照してください](configure-global-settings-for-safe-links.md)。

  ただし、365 のアプリOfficeリンク保護は、アクティブなセーフリンク ポリシーに含まれるユーザーにのみ適用されます。 ユーザーがアクティブなセーフ リンク ポリシーに含まれていない場合、ユーザーはサポートされている 365 アプリでセーフ リンクOfficeされません。

  Office 365 アプリのセーフ リンク保護の詳細については、この記事の「Office [365](#safe-links-settings-for-office-365-apps) アプリのセーフ リンク設定」セクションを参照してください。

この記事では、次の種類のセーフ リンク設定の詳細な説明について説明します。

- **セーフ リンク ポリシーの設定**: これらの設定は、特定のポリシーに含まれるユーザーにのみ適用され、ポリシー間で設定が異なる場合があります。 これらの設定には、次のものが含まれます。

  - [電子メール メッセージの安全なリンク設定](#safe-links-settings-for-email-messages)
  - [Microsoft Teams の安全なリンク設定](#safe-links-settings-for-microsoft-teams)
  - [セーフ リンク ポリシーの "次の URL を書き換えない" リスト](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **グローバル セーフ リンクの設定**: これらの設定は、セーフ リンク ポリシーではなく、グローバルに構成されます。 ただし、この設定は、アクティブなセーフ リンク ポリシーに含まれているユーザーにのみ適用されます。 これらの設定には、次のものが含まれます。

  - [365 アプリの安全Office設定](#safe-links-settings-for-office-365-apps)
  - [セーフ リンクの "次の URL をブロックする" リスト](#block-the-following-urls-list-for-safe-links)

次の表では、Microsoft 365 および Office 365 の Defender for Office 365 を含む組織のセーフ リンクのシナリオについて説明します (つまり、ライセンスの不足は、例では決して問題ではありません)。

****

|シナリオ|結果|
|---|---|
|Jean はマーケティング部門のメンバーです。 Office 365 アプリのセーフ リンク保護は、セーフ リンクのグローバル設定で有効にされ、マーケティング部門のメンバーに適用されるセーフ リンク ポリシーが存在します。 Jean は、電子メール メッセージで PowerPoint プレゼンテーションを開き、プレゼンテーション内の URL をクリックします。|Jean はセーフ リンクによって保護されています。 <p> Jean はセーフ リンク ポリシーに含まれており、365 アプリの安全Office保護が有効です。 <p> Office 365 アプリのセーフ リンク保護の要件の詳細については、この記事の後半の [「Office 365](#safe-links-settings-for-office-365-apps) アプリのセーフ リンク設定」セクションを参照してください。|
|Chris の Microsoft 365 E5 組織には、セーフ リンク ポリシーが構成されていません。 Chris は、最終的にクリックする悪意のある Web サイトへの URL を含む外部送信者からメールを受信します。|Chris はセーフ リンクによって保護されません。 <p> 管理者は、受信電子メール メッセージでセーフ リンク保護を取得するために、すべてのユーザーに対して少なくとも 1 つのセーフ リンク ポリシーを作成する必要があります。 安全なリンク保護を取得するには、ポリシーの条件に Chris を含める必要があります。|
|Pat の組織では、管理者はセーフ リンク ポリシーを作成していなかっていますが、365 アプリのセーフ Office保護が有効になります。 Pat は Word ドキュメントを開き、ファイル内の URL をクリックします。|Pat はセーフ リンクで保護されません。 <p> Office 365 アプリの安全なリンク保護はグローバルに有効になりますが、Pat はアクティブなセーフ リンク ポリシーには含まれていないので、保護を適用できます。|
|Lee の組織では、セーフ リンクのグローバル設定の [次の URL をブロックする] `https://tailspintoys.com` リストで構成されます。  Lee を含むセーフ リンク ポリシーが既に存在します。 Lee は URL を含む電子メール メッセージを受信します `https://tailspintoys.com/aboutus/trythispage` 。 Lee が URL をクリックします。|Lee の URL が自動的にブロックされる場合があります。リスト内の URL エントリと、使用するメール クライアント Lee によって異なります。 詳細については、この記事の [後半](#block-the-following-urls-list-for-safe-links) の「安全なリンク」セクションの「次の URL をブロックする」の一覧を参照してください。|
|Jamie と Julia は両方とも、contoso.com。 長い時間前、管理者は Jamie と Julia の両方に適用されるセーフ リンク ポリシーを構成しました。 Jamie は、電子メールに悪意のある URL が含まれていることを知らずに、電子メールを Julia に送信します。|Julia は、内部受信者間のメッセージに適用するセーフ リンク ポリシーが構成されている場合、セーフ リンクによって保護されます。 詳細については、この記事の後半の「電子メール メッセージの安全 [なリンク設定](#safe-links-settings-for-email-messages) 」セクションを参照してください。|

## <a name="safe-links-settings-for-email-messages"></a>電子メール メッセージの安全なリンク設定

セーフ リンクは、既知の悪意のあるハイパーリンクの受信メールをスキャンします。 スキャンされた URL は、Microsoft 標準 URL プレフィックスを使用して書き `https://nam01.safelinks.protection.outlook.com` 換えされます。 リンクの書き換え後、悪意のある可能性のあるコンテンツについて分析されます。

セーフ リンクが URL を書き換えた後、メッセージが手動で転送または返信された (内部受信者と外部受信者の両方) 場合でも、URL は書き換えたままです。 転送またはメッセージへの返信に追加される追加のリンクは書き換えされません。 ただし、受信トレイ ルールまたは SMTP 転送による自動転送の場合、その受信者がセーフ リンクによって保護されている場合や、以前の通信でURL が既に書き換え済みである場合を限り、最終的な受信者を対象としたメッセージに URL は書き換えされません。 

電子メール メッセージに適用されるセーフ リンク ポリシーの設定については、次の一覧で説明します。

- **メッセージ内の不明な潜在的に悪意** のある URL のアクションを選択します。電子メール メッセージのセーフ リンク スキャンを有効または無効にします。 推奨される値は **On です**。 この設定を有効にすると、次の操作が実行されます。

  - Windows の Outlook (C2R) で安全なリンクのスキャンが有効になります。
  - URL が書き換えされ、メッセージ内の URL をクリックすると、ユーザーはセーフ リンク保護を介してルーティングされます。
  - クリックすると、既知の悪意のある URL の一覧と [次の URL をブロックする] リストに対して [URL がチェックされます](#block-the-following-urls-list-for-safe-links)。
  - 有効な評価を持つ URL は、バックグラウンドで非同期的に無効になります。

- **ファイルを指** す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する: ダウンロード可能なコンテンツを指す電子メール メッセージ内のリンクを含む、リンクのリアルタイム スキャンを有効にする。 推奨される値は有効です。

  - **メッセージを配信する前に URL のスキャンが完了するのを待ちます**。

    - 有効: URL を含むメッセージは、スキャンが完了するまで保持されます。 メッセージは、URL が安全と確認された後にのみ配信されます。 これは推奨される値です。
    - 無効: URL スキャンを完了できない場合は、メッセージを配信します。

- **組織内で送信** される電子メール メッセージに安全なリンクを適用する: 内部送信者と同じ Exchange Online 組織内の内部受信者間で送信されるメッセージに対するセーフ リンク スキャンを有効または無効にします。 推奨される値は有効です。

- **ユーザーのクリックを追跡しない**: 電子メール メッセージでクリックされた URL のセーフ リンク クリック データの保存を有効または無効にします。 推奨値は、この設定を選択しないままにすることをお勧めします (ユーザーのクリックを追跡する場合)。

  内部送信者と内部受信者の間で送信される電子メール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。

- **ユーザーに元の URL** へのクリックを許可しない : 警告ページから元の [](#warning-pages-from-safe-links)URL へのクリックをユーザーに許可またはブロックします。 推奨値が有効です。

- **通知ページと警告ページに組織** のブランド化を表示する: このオプションは、警告ページに組織のブランド化を表示します。 ブランド化は、既定の Microsoft 警告ページが攻撃者によって頻繁に使用されるので、ユーザーが正当な警告を識別するのに役立ちます。 カスタマイズされたブランド化の詳細については、「組織の Azure Active Directory サインイン ページにブランド化を追加する [」を参照してください](/azure/active-directory/fundamentals/customize-branding)。

- **次の URL を書き換えない**: URL は変更しない。 スキャンを必要としない安全な URL のカスタム リストを保持します。 リストは、各セーフ リンク ポリシーで一意です。 [次の URLを書き換えない] リストの詳細[](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)については、この記事の後半の「セーフ リンク ポリシー」の「次の URL を書き換えない」リストを参照してください。

安全なリンク ポリシーの Standard および Strict ポリシー設定の推奨値の詳細については、「セーフ リンク ポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

- **受信者フィルター**: ポリシーが適用されるユーザーを決定する受信者の条件と例外を指定する必要があります。 条件や例外には次のプロパティを使用できます。

  - **受信者が次の場合**
  - **受信者ドメインは、**
  - **受信者が次のメンバーの場合**

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

- **優先度**: 複数のポリシーを作成する場合は、適用する順序を指定できます。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

  優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

### <a name="how-safe-links-works-in-email-messages"></a>電子メール メッセージでのセーフ リンクの動作

電子メール メッセージ内の URL に対するセーフ リンク保護の仕組みについて、大まかに説明します。

1. メッセージが受信者のメールボックスに配信される前に、すべての電子メールは EOP を通過します。ここで、インターネット プロトコル (IP) およびエンベロープ フィルター、署名ベースのマルウェア保護、スパム対策およびマルウェア対策フィルター。

2. ユーザーは自分のメールボックスでメッセージを開き、メッセージ内の URL をクリックします。

3. セーフ リンクは、Web サイトを開く前に URL をすぐに確認します。

   - URL が [次の URL をブロックする] リストに **含** まれている場合は、ブロックされた [URL 警告が開](#blocked-url-warning) きます。

   - URL が悪意のあると判断された Web サイトを参照している場合[](#malicious-website-warning)は、悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し示し、[ファイルをポイントする疑わしいリンクとリンクのリアルタイム **URL** スキャンを適用する] 設定が、ユーザーに適用されるポリシーで有効になっている場合、ダウンロード可能なファイルがチェックされます。

   - URL が安全と判断された場合、Web サイトが開きます。

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft Teams の安全なリンク設定

> [!IMPORTANT]
> 2020 年 3 月現在、この機能はプレビューで、Microsoft Teams テクノロジ導入プログラム (TAP) のメンバーにのみ利用できます。 リリース スケジュールの詳細については [、「Microsoft 365 ロードマップ」を参照してください](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。

セーフ リンク ポリシーで Microsoft Teams のセーフ リンク保護を有効または無効にします。 具体的には、[Microsoft Teams 内の不明な URL または潜在的に悪意のある URL のアクションを選択する] **設定を使用** します。 推奨される値は **On です**。

電子メール メッセージ内のリンクに適用されるセーフ リンク ポリシーの次の設定は、Teams のリンクにも適用されます。

- **ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する**
- **ユーザーのクリックを追跡しない**
- **ユーザーに元の URL へのクリックを許可しない**

これらの設定については、「電子メール メッセージの安全 [なリンクの設定」セクションで説明](#safe-links-settings-for-email-messages) します。

Microsoft Teams の安全なリンク保護を有効にすると、保護されたユーザーがリンクをクリックすると、Teams の URL が既知の悪意のあるリンクの一覧に対してチェックされます (クリック時の保護)。 URL は書き換え用ではありません。 リンクが悪意のあると判明した場合、ユーザーには次のエクスペリエンスがあります。

- Teams の会話、グループ チャット、またはチャネルでリンクがクリックされた場合、次のスクリーンショットに示すように警告ページが既定の Web ブラウザーに表示されます。
- ピン留めされたタブからリンクがクリックされた場合、警告ページはタブ内の Teams インターフェイスに表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由から無効になっています。
- ポリシーの [ユーザーによる元の URL へのクリックを許可しない] 設定の構成方法に応じて、ユーザーは元の **URL** (スクリーンショットの [続行] (推奨しない **)** をクリックするか、または許可されません。 ユーザーが元の URL をクリックできない場合は、[ユーザーが元の **URL** をクリックすることを許可しない] 設定を有効にすることをお勧めします。

リンクを送信したユーザーが Teams 保護が有効になっているセーフ リンク ポリシーに含まれていない場合、ユーザーはコンピューターまたはデバイス上の元の URL を自由にクリックできます。

![悪意のあるリンクを報告する Teams の安全なリンク ページ。](../../media/tp-safe-links-for-teams-malicious.png)

警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。 ただし、元のリンクを再度クリックすると、セーフ リンクが URL を再スキャンし、警告ページが再表示されます。

### <a name="how-safe-links-works-in-teams"></a>Teams での安全なリンクの動作

Microsoft Teams の URL に対するセーフ リンク保護の仕組みは、大まかです。

1. ユーザーが Teams アプリを起動します。

2. Microsoft 365 は、ユーザーの組織に Office 365 用 Microsoft Defender が含まれており、Microsoft Teams の保護が有効になっているアクティブなセーフ リンク ポリシーにユーザーが含まれているか確認します。

3. URL は、チャット、グループ チャット、チャネル、およびタブ内のユーザーのクリック時に検証されます。

## <a name="safe-links-settings-for-office-365-apps"></a>365 アプリの安全Office設定

Office 365 アプリの安全なリンク保護は、電子メール メッセージ内のリンクではなく Office ドキュメント内のリンクをチェックします (ただし、ドキュメントを開いた後、電子メール メッセージ内の添付 Office ドキュメントのリンクをチェックできます)。

365 のアプリOfficeの安全なリンク保護には、次のクライアント要件があります。

- Microsoft 365 Apps または Microsoft 365 Business Premium。
  - Windows、Mac、または Web ブラウザーの Word、Excel、PowerPoint の現在のバージョン。
  - Office Android デバイス上のアプリを使用します。
  - Visio on Windows。
  - Web ブラウザーの OneNote。

- Office 365 アプリは、最新の認証を使用するように構成されています。 詳細については、「最新の認証が [2016、Office 2013 2016、Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md)クライアント アプリでどのように機能Officeか」を参照してください。

- ユーザーは、自分の仕事または学校のアカウントを使用してサインインします。 詳細については、「サインインしてサインイン[する」を参照Office。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

セーフ リンクポリシーではなく、Officeリンクのグローバル設定で、365 アプリのセーフ リンク保護を構成します。 ただし、Office 365 アプリのセーフ リンク保護を適用するには、Office ドキュメントを開いてリンクをクリックするユーザーは、アクティブなセーフ リンク ポリシーに含める必要があります。

次のセーフ リンク設定は、365 アプリOffice使用できます。

- **Office 365 アプリケーション**: サポートされている 365 アプリでセーフ リンク スキャンOfficeまたは無効にします。 既定値と推奨値は On **です**。

- **ユーザーが**[安全なリンク] をクリックしても追跡しない : デスクトップ バージョンの Word、Excel、PowerPoint、Visio でクリックされた URL のセーフ リンク クリック データの保存を有効または無効にします。 推奨される値は **Off** です。つまり、ユーザーのクリックが追跡されます。

- **ユーザー** が元の URL への安全なリンクをクリックさせない : ユーザーが警告 [](#warning-pages-from-safe-links)ページをクリックして、デスクトップ バージョンの Word、Excel、PowerPoint、Visio の元の URL に対してクリックを許可またはブロックします。 既定値と推奨値は On **です**。

365 アプリのセーフ リンクOffice構成するには、「Configure Safe Links protection for Office [365 アプリ」を参照してください](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)。

Standard および Strict ポリシー設定の推奨値の詳細については、「セーフ リンクの [グローバル設定」を参照してください](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。

### <a name="how-safe-links-works-in-office-365-apps"></a>365 アプリでセーフ リンクOffice動作する方法

365 アプリの URL に対するセーフ リンク保護の仕組Office示します。 365 Officeサポートされているアプリについては、前のセクションで説明します。

1. ユーザーは、Microsoft 365 Apps または Microsoft 365 Business Premium を含む組織内の仕事または学校のアカウントを使用してサインインします。

2. ユーザーが開き、サポートされているアプリ内OfficeドキュメントのリンクをOfficeします。

3. セーフ リンクは、ターゲット Web サイトを開く前に URL をすぐに確認します。

   - 安全なリンクのスキャンをスキップする URL がリストに含まれている場合([次の URL をブロックする] ボックスの一覧)、ブロックされた URL 警告[ページが開](#blocked-url-warning)きます。

   - URL が悪意のあると判断された Web サイトを参照している場合[](#malicious-website-warning)は、悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し示し、ユーザーに適用されるセーフ リンク ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (ファイルを指す疑わしいリンクやリンクに対してリアルタイム **URL** スキャンを適用する) 場合は、ダウンロード可能なファイルがチェックされます。

   - URL が安全であると見なされた場合、ユーザーは Web サイトにアクセスされます。

   - セーフ リンクのスキャンを完了できない場合、セーフ リンク保護はトリガーされない。 デスクトップ Officeでは、ユーザーが宛先 Web サイトに進む前に警告が表示されます。

> [!NOTE]
> 各セッションの開始時に、ユーザーが安全なリンクを有効にOfficeがあります。

## <a name="block-the-following-urls-list-for-safe-links"></a>セーフ リンクの "次の URL をブロックする" リスト

[ **次の URL をブロックする** ] ボックスの一覧では、次の場所でセーフ リンク スキャンによって常にブロックされるリンクを定義します。

- 電子メール メッセージ
- Windows と Mac Office 365 アプリ内のドキュメント。
- iOS Office Android 用のドキュメント。

アクティブなセーフ リンク ポリシーのユーザーが、サポートされているアプリ内のブロックされたリンクをクリックすると、[ブロックされた URL 警告] [ページに移動](#blocked-url-warning) します。

セーフ リンクのグローバル設定で URL の一覧を構成します。 手順については [、「Configure the Configure the following URL」リストを参照してください](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。

**注**:

- あらゆる場所でブロックされている URL の本当に汎用的なリストについては、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。

- 制限:
  - エントリの最大数は 500 です。
  - エントリの最大長は 128 文字です。
  - すべてのエントリは、10,000 文字を超えることはできません。

- URL の末尾にスラッシュ ( ) を `/` 含めない。 たとえば、 を `https://www.contoso.com` 使用します `https://www.contoso.com/` 。

- ドメイン専用 URL (たとえば、または) は、ドメインを含む `contoso.com` `tailspintoys.com` すべての URL をブロックします。

- 完全なドメインをブロックせずにサブドメインをブロックできます。 たとえば、サブドメインを含む URL をブロックしますが、完全なドメインを含む `toys.contoso.com*` URL はブロックしない `contoso.com` 。

- URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"次の URL をブロックする" リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

****

|値|結果|
|---|---|
|`contoso.com` <p> または <p> `*contoso.com*`|ドメイン、サブドメイン、およびパスをブロックします。 たとえば `https://www.contoso.com` `https://sub.contoso.com` 、、、 `https://contoso.com/abc` およびブロックされます。|
|`https://contoso.com/a`|ブロック `https://contoso.com/a` ですが、追加のサブパスはブロックしない `https://contoso.com/a/b` 。|
|`https://contoso.com/a*`|ブロック `https://contoso.com/a` や追加のサブパス `https://contoso.com/a/b` (.|
|`https://toys.contoso.com*`|サブドメイン (この例では) をブロックしますが、他のドメイン URL (など) へのクリック `toys` を `https://contoso.com` 許可 `https://home.contoso.com` します。|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>セーフ リンク ポリシーの "次の URL を書き換えない" リスト

> [!NOTE]
> 組織でセーフ リンク ポリシーを使用している場合は、サードパーティのフィッシング テストでサポートされている唯一の方法は、次の **URL** リストを書き換えない方法です。

各セーフ リンク ポリシーには、セーフ リンク スキャンによって書き換えされない URL を指定するために使用できる次の URL リストを書き換えないが含まれます。 つまり、ポリシーに含まれるユーザーは、セーフ リンクによってブロックされる指定された URL にアクセスできます。 さまざまなセーフ リンク ポリシーでさまざまなリストを構成できます。 ポリシー処理は、最初の (優先度が最も高い) ポリシーがユーザーに適用された後に停止します。 したがって **、1 つのみ次の URL** リストを書き換えないと、複数のアクティブなセーフ リンク ポリシーに含まれるユーザーに適用されます。

新規または既存のセーフ リンク ポリシーのリストにエントリを追加するには、「Create Safe [Links policies](set-up-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) or [Modify Safe Links policies」を参照してください](set-up-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。

**注**:

- 次のクライアントは、セーフ リンク ポリシーの [次の URL を書き **換** えない] リストを認識しません。 ポリシーに含まれるユーザーは、次のクライアントでのセーフ リンク スキャンの結果に基づいて URL へのアクセスをブロックできます。

  - Microsoft Teams
  - Office Web アプリ

  すべての場所で許可されている URL の本当に汎用的なリストについては [、「Manage the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。

- ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加する方法を検討してください。 たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。

- [セーフ リンク] ポリシーで次の **URL** エントリを書き換えない場合は、リストを確認し、必要に応じてワイルドカードを追加してください。 たとえば、リストには次のようなエントリが含まれるので、後で次のような `https://contoso.com/a` サブパスを含めることにしました `https://contoso.com/a/b` 。 新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、 `https://contoso.com/a/*` になります。

- URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。 ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。 たとえば、指定したドメイン内のサブドメインとパスをユーザーがアクセスできるので、エントリは同 `contoso.com` `*.contoso.com/*` `*.contoso.com/*` じではありません。

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"次の URL を書き換えない" リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

****

|値|結果|
|---|---|
|`contoso.com`|サブドメインまたは `https://contoso.com` パスへのアクセスを許可しますが、アクセスを許可しない。|
|`*.contoso.com/*`|ドメイン、サブドメイン、およびパス (たとえば、) へのアクセス `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` を許可します `https://www.contoso.com/a` 。 <p> このエントリは、潜在的に詐欺的なサイトを許可しないので、本来よりも `*contoso.com*` 優れた方法 `https://www.falsecontoso.com` です。 `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|サブパスへの `https://contoso.com/a` アクセスを許可しますが、サブパスは許可しない `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|次のようなアクセス `https://contoso.com/a` とサブパスを許可します `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>セーフ リンクからの警告ページ

このセクションでは、URL をクリックするとセーフ リンク保護によってトリガーされるさまざまな警告ページの例を示します。

いくつかの警告ページが更新された点に注意してください。 更新されたページがまだ表示されていない場合は、すぐに表示されます。 更新されたページには、新しい配色、詳細、および指定された警告と推奨事項にもかかわらずサイトに進む機能が含まれます。

### <a name="scan-in-progress-notification"></a>進行中の通知をスキャンする

クリックされた URL は、セーフ リンクによってスキャンされています。 リンクを再度試す前に、しばらく待つ必要がある場合があります。

!["リンクがスキャン中" 通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

元の通知ページは次のように表示されます。

![元の "リンクがスキャン中" 通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>疑わしいメッセージの警告

クリックされた URL は、他の疑わしいメッセージに似た電子メール メッセージに含まれます。 サイトに進む前に、電子メール メッセージをもう一度確認することをお勧めします。

!["疑わしいメッセージからリンクがクリックされました" という警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>フィッシングの試行の警告

クリックされた URL は、フィッシング攻撃として識別された電子メール メッセージに含めでした。 その結果、電子メール メッセージ内のすべての URL がブロックされます。 サイトに進むのはやめすることをお勧めします。

!["フィッシング メッセージからリンクがクリックされました" という警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>悪意のある Web サイトの警告

クリックされた URL は、悪意のあるサイトをポイントします。 サイトに進むのはやめすることをお勧めします。

![「この Web サイトは悪意のある Web サイトに分類されます」という警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

元の警告ページは次のように表示されます。

![元の "この Web サイトは悪意のある Web サイトとして分類されています" という警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>ブロックされた URL の警告

クリックされた URL は、組織内の管理者によって手動でブロックされています (セーフ リンクのグローバル設定の [次の **URL** をブロックする] リスト)。 リンクは手動でブロックされたため、セーフ リンクによってスキャンされません。

管理者が特定の URL を手動でブロックする理由は複数あります。 サイトをブロックしない場合は、管理者に問い合わせください。

!["この Web サイトは管理者によってブロックされました" という警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

元の警告ページは次のように表示されます。

![元の "この Web サイトは、組織の URL ポリシーごとにブロックされています" という警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>エラー警告

何らかのエラーが発生し、URL を開くことができません。

![「アクセスしようとしているページを読み込め」という警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

元の警告ページは次のように表示されます。

![元の "この Web ページを読み込めない" という警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
