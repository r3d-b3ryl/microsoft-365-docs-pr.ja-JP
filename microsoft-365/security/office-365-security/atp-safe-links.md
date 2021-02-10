---
title: 安全なリンク
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
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
description: この記事では、管理者は、フィッシングや悪意のある URL を使用するその他の攻撃から組織を保護するために、Office 365 の Defender の安全なリンク保護について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 251b3e71be30f90ac828abc8bf34877d65615336
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175777"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全なリンク

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用している場合、Outlook のセーフリンクに関する情報を探している場合は [、「Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

「安全なリンク」は [、Defender for Office 365](office-365-atp.md) の機能で、メール フロー内の受信メール メッセージの URL のスキャンと書き換え、および電子メール メッセージや他の場所での URL とリンクのクリック時の検証を提供します。 安全なリンクのスキャンは、Exchange Online [](anti-spam-and-anti-malware-protection.md) Protection (EOP) の受信電子メール メッセージの通常のスパム対策およびマルウェア対策保護に加えて行われます。 安全なリンクのスキャンは、フィッシングなどの攻撃で使用される悪意のあるリンクから組織を保護するのに役立ちます。

安全なリンク保護は、次の場所で利用できます。

- **電子メール メッセージ**: 電子メール メッセージ内のリンクに対する安全なリンク保護は、安全なリンク ポリシーによって制御されます。 既定の安全なリンクポリシーはないので、電子メール メッセージ内の安全なリンクの保護を取得するには、1 つ以上の安全なリンク ポリシーを作成 **する必要があります**。 手順については、「Microsoft Defender で安全なリンク ポリシーをセットアップする [(Office 365)」を参照](set-up-atp-safe-links-policies.md)してください。

  電子メール メッセージの安全なリンク保護の詳細については、[](#safe-links-settings-for-email-messages)この記事の後半の「電子メール メッセージの安全なリンクの設定」を参照してください。

- **Microsoft Teams** (現在 TAP プレビュー): Teams の会話、グループ チャット、またはチャネルからのリンクに対する安全なリンク保護も、安全なリンク ポリシーによって制御されます。 既定の安全なリンクポリシーはないので、Teams の安全なリンクの保護を取得するには、1 つ以上の安全なリンク ポリシーを作成 **する必要があります**。

  Teams での安全なリンク保護の詳細については、この記事の後半にある [「Microsoft Teams](#safe-links-settings-for-microsoft-teams) の安全なリンク設定」セクションを参照してください。

- **Office 365 アプリ**: Office 365 アプリの安全なリンク保護は、サポートされているデスクトップ、モバイル、および Web AP で利用できます。 365 アプリの安全Office保護は、安全なリンク ポリシーの外部にあるグローバル設定で構成します。  手順については [、「Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)での安全なリンク設定のグローバル設定を構成する」を参照してください。

  ただし、Office 365 アプリの安全なリンク保護は、アクティブな安全なリンク ポリシーに含まれているユーザーにのみ適用されます。 ユーザーがアクティブな安全なリンク ポリシーに含まれていない場合、ユーザーはサポートされている 365 アプリで安全なリンクOfficeされません。

  Office 365 アプリの安全なリンク保護の詳細については、この記事の後半にある [「Office 365](#safe-links-settings-for-office-365-apps) アプリの安全なリンク設定」セクションを参照してください。

この記事では、次の種類の安全なリンク設定について詳しく説明します。

- **安全なリンク** ポリシーの設定 : これらの設定は、特定のポリシーに含まれるユーザーにのみ適用され、ポリシーによって設定が異なる場合があります。 これらの設定には次のものがあります。

  - [電子メール メッセージの安全なリンク設定](#safe-links-settings-for-email-messages)
  - [Microsoft Teams の安全なリンク設定](#safe-links-settings-for-microsoft-teams)
  - [「安全なリンク」ポリシーの「次の URL を書き換えない」](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **グローバル な安全なリンク** の設定 : これらの設定は、安全なリンク ポリシーではなくグローバルに構成されます。 ただし、この設定は、アクティブな安全なリンク ポリシーに含まれているユーザーにのみ適用されます。 これらの設定には次のものがあります。

  - [365 アプリの安全Office設定](#safe-links-settings-for-office-365-apps)
  - [「安全なリンク」の「次の URL をブロックする」の一覧](#block-the-following-urls-list-for-safe-links)

次の表では、Defender for Office 365 を含む Microsoft 365 および Office 365 組織の安全なリンクのシナリオについて説明します (つまり、例ではライセンスの不足は決して問題ではありません)。

****

|シナリオ|結果|
|---|---|
|マーケティング部門のメンバーです。 Office 365 アプリの安全なリンク保護は、安全なリンクのグローバル設定で有効にされ、マーケティング部門のメンバーに適用される安全なリンク ポリシーが存在します。 電子メール メッセージで PowerPoint プレゼンテーションを開き、プレゼンテーションの URL をクリックします。|安全なリンクによって保護されています。 <p> 「安全なリンク」ポリシーには「安全なリンク」ポリシーが含まれており、365 Officeの安全なリンク保護が有効になっている。 <p> Office 365 アプリの安全なリンク保護の要件の詳細については、この記事の後半にある [「Office 365](#safe-links-settings-for-office-365-apps) アプリの安全なリンク設定」セクションを参照してください。|
|Chris の Microsoft 365 E5 組織には、安全なリンクポリシーが構成されていません。 Chris は、最終的にクリックする悪意のある Web サイトへの URL を含むメールを外部送信者から受信します。|Chris は安全なリンクによって保護されません。 <p> 管理者は、受信電子メール メッセージで安全なリンク保護を取得するために、すべてのユーザーに対して少なくとも 1 つの安全なリンク ポリシーを作成する必要があります。 Chris は、安全なリンク保護を得るポリシーの条件に含める必要があります。|
|Pat の組織では、管理者は安全なリンク ポリシーを作成していなが、Office 365 アプリの安全なリンク保護が有効になっている。 Pat は Word 文書を開き、ファイル内の URL をクリックします。|Pat は安全なリンクによって保護されません。 <p> Office 365 アプリの安全なリンク保護はグローバルに有効になりますが、Pat はアクティブな安全なリンク ポリシーに含まれていないので、保護は適用されません。|
|In Lee's organization, `https://tailspintoys.com` is configured in the **Block the following URLs** list in the global settings for Safe Links. Lee を含む安全なリンク ポリシーは既に存在します。 Lee は URL を含む電子メール メッセージを受信します `https://tailspintoys.com/aboutus/trythispage` 。 Lee が URL をクリックします。|Url は自動的に Lee に対してブロックされる場合があります。リスト内の URL エントリと、使用される電子メール クライアントの Lee によって異なります。 詳細については、この記事の後半にある「安全なリンク [」](#block-the-following-urls-list-for-safe-links) の「次の URL をブロックする」の一覧を参照してください。|
|Jamie と Julia は、どちらも contoso.com。 長い間、管理者は Jamie と Julia の両方に適用される安全なリンク ポリシーを構成していました。 Jamie は、電子メールに悪意のある URL が含まれているのを知らずに、Julia にメールを送信します。|Julia は、彼女に適用される安全なリンク ポリシーが内部受信者間のメッセージに適用するように構成されている場合、安全なリンクによって保護されます。 詳細については、この記事の後半にある「電子メール メッセージの [安全なリンク](#safe-links-settings-for-email-messages) 設定」を参照してください。|

## <a name="safe-links-settings-for-email-messages"></a>電子メール メッセージの安全なリンク設定

「安全なリンク」は、受信メールをスキャンして既知の悪意のあるハイパーリンクを検出します。 スキャンされた URL は、Microsoft 標準 URL プレフィックスを使用して書き換えされます `https://nam01.safelinks.protection.outlook.com` 。 リンクの書き換え後、悪意のある可能性のあるコンテンツが分析されます。

安全なリンクが URL を書き換えた後、メッセージが転送または返信された場合でも、URL は書き換えたままです。 転送またはメッセージに返信される追加のリンクは書き換えされません。

電子メール メッセージに適用される安全なリンク ポリシーの設定について、次の一覧で説明します。

- **メッセージ内の悪意のある可能性** のある不明な URL に対するアクションを選択します。電子メール メッセージの安全なリンクのスキャンを有効または無効にします。 推奨される値は **On です**。 この設定を有効にすると、次の操作が実行されます。

  - 安全なリンクのスキャンは、Windows の Outlook (C2R) で有効になっています。
  - URL が書き換えされ、メッセージ内の URL をクリックすると、ユーザーは安全なリンク保護によってルーティングされます。
  - クリックすると、既知の悪意のある URL の一覧と "次の URL をブロックする" リストに対して [URL がチェックされます](#block-the-following-urls-list-for-safe-links)。
  - 有効な評価を持たなかった URL は、バックグラウンドで非同期的にデトニトされます。

- **疑わしいリンク** やファイルを指すリンクに対してリアルタイム URL スキャンを適用します。ダウンロード可能なコンテンツを指す電子メール メッセージ内のリンクなど、リンクをリアルタイムでスキャンできます。 推奨値は有効です。

  - **メッセージを配信する前に URL のスキャンが完了するのを待ちます**。

    - 有効: URL を含むメッセージは、スキャンが完了するまで保持されます。 メッセージは、URL が安全だと確認された後にのみ配信されます。 これは推奨値です。
    - 無効: URL のスキャンを完了できない場合は、メッセージを配信します。

- **組織内で** 送信される電子メール メッセージに安全なリンクを適用する : 内部送信者と同じ Exchange Online 組織内の内部受信者の間で送信されるメッセージに対する安全なリンクのスキャンを有効または無効にします。 推奨値は有効です。

- **ユーザーのクリックを** 追跡しない : 電子メール メッセージでクリックされた URL の安全なリンク のクリック データの保存を有効または無効にします。 推奨値は、この設定を未選択のままにする (ユーザーのクリックを追跡する) 方法です。

  内部送信者と内部受信者の間で送信される電子メール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。

- **ユーザーがクリックして元** の URL に移動できない: ユーザーが警告ページをクリックして元の URL [を](#warning-pages-from-safe-links) クリックできないかブロックします。 推奨値は有効です。

- **次の URL は書き換え** ない : URL は変更しない。 スキャンを必要としない安全な URL のカスタム リストを保持します。 リストは、安全なリンク ポリシーごとに一意です。 [次の URLを書き換えない] の一覧[](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)の詳細については、この記事の後半にある「安全なリンク ポリシー」の「次の URL を書き換えない」の一覧を参照してください。

安全なリンク ポリシーの標準および厳密なポリシー設定の推奨値の詳細については、「安全なリンクのポリシー設定 [」を参照してください](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

- **受信者フィルター**: ポリシーを適用するユーザーを決定する受信者の条件と例外を指定する必要があります。 条件や例外には次のプロパティを使用できます。

  - **受信者が次の場合**
  - **受信者のドメインが次の場合**
  - **受信者が次のメンバーの場合**

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

- **優先度**: 複数のポリシーを作成する場合は、適用する順序を指定できます。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

  優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

### <a name="how-safe-links-works-in-email-messages"></a>電子メール メッセージでの安全なリンクのしくみ

電子メール メッセージの URL で安全なリンク保護がどのように機能するのか、大まかには次のように説明します。

1. すべての電子メールは EOP を経由します。EOP では、メッセージが受信者のメールボックスに配信される前に、インターネット プロトコル (IP) およびエンベロープ フィルター、署名ベースのマルウェア保護、スパム対策およびマルウェア対策フィルターが適用されます。

2. ユーザーは自分のメールボックスでメッセージを開き、メッセージ内の URL をクリックします。

3. 安全なリンクは、Web サイトを開く前に URL をすぐに確認します。

   - URL が [次の URL **をブロックする** ] ボックスの一覧に含まれている場合は、ブロックされた [URL の警告が表示](#blocked-url-warning) されます。

   - URL が悪意のあると判断された Web サイトをポイントすると、[](#malicious-website-warning)悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し示し、ユーザーに適用されるポリシーで [疑わしいリンクとファイルを指すリンクのリアルタイム **URL** スキャンの適用] 設定が有効になっている場合は、ダウンロード可能なファイルがチェックされます。

   - URL が安全だと判断された場合は、Web サイトが開きます。

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft Teams の安全なリンク設定

> [!IMPORTANT]
> 2020 年 3 月現在、この機能はプレビュー中であり、Microsoft Teams テクノロジ導入プログラム (TAP) のメンバーだけが利用できます。 リリース スケジュールの詳細については [、Microsoft 365 ロードマップを参照してください](https://www.microsoft.com/microsoft-365/roadmap?rtc=1&filters=&searchterms=Safe%2CLinks%2CProtection%2Cfor%2CMicrosoft%2CTeams)。

Microsoft Teams の安全なリンク保護は、安全なリンク ポリシーで有効または無効にします。 具体的には、[Microsoft Teams 内の不明な URL または悪意のある可能性のある URL に対してアクションを選択する **] 設定を使用** します。 推奨される値は **On です**。

メール メッセージ内のリンクに適用される安全なリンク ポリシーの次の設定は、Teams のリンクにも適用されます。

- **ファイルを指す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する**
- **ユーザーのクリックを追跡しない**
- **ユーザーがクリックして元の URL にアクセスできない**

これらの設定については、前の「電子メール メッセージの [安全なリンク設定」セクションで説明](#safe-links-settings-for-email-messages) されています。

Microsoft Teams の安全なリンク保護を有効にすると、保護されたユーザーがリンクをクリックすると、Teams の URL が既知の悪意のあるリンクの一覧に対してチェックされます (クリック時の保護)。 URL は書き換えではありません。 悪意のあるリンクが見つかった場合、ユーザーは次のエクスペリエンスを利用できます。

- Teams の会話、グループ チャット、またはチャネルからリンクがクリックされた場合、次のスクリーンショットに示すように警告ページが既定の Web ブラウザーに表示されます。
- 固定されたタブからリンクがクリックされた場合、そのタブ内の Teams インターフェイスに警告ページが表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由から無効になっています。
- ポリシーの [ユーザーがクリックして元の URL に戻せない] 設定の構成方法に応じて、ユーザーはクリックして元の **URL** に進むか許可されません (スクリーンショットでは続行 **します (** 推奨されません)。 ユーザーがクリックして元の URL にアクセスすることを許可しない設定を有効にし、ユーザーがクリックして元の **URL** にアクセスすることを許可することをお勧めします。

リンクを送信したユーザーが、Teams の保護が有効になっている安全なリンク ポリシーに含まれていない場合、ユーザーは自分のコンピューターまたはデバイス上の元の URL まで自由にクリックスルーできます。

![悪意のあるリンクを報告する Teams の安全なリンク ページ。](../../media/tp-safe-links-for-teams-malicious.png)

警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。 ただし、元のリンクを再度クリックすると、安全なリンクによって URL が再スキャンされます。そのため、警告ページが再表示されます。

### <a name="how-safe-links-works-in-teams"></a>Teams での安全なリンクのしくみ

Microsoft Teams の URL に対する安全なリンク保護のしくみを大まかに次に示します。

1. ユーザーが Teams アプリを起動します。

2. Microsoft 365 は、ユーザーの組織に Office 365 用 Microsoft Defender が含まれており、Microsoft Teams の保護が有効になっているアクティブな安全なリンク ポリシーにユーザーが含まれているか確認します。

3. URL は、ユーザーがチャット、グループ チャット、チャネル、タブをクリックした時点で検証されます。

## <a name="safe-links-settings-for-office-365-apps"></a>365 アプリの安全Office設定

Office 365 アプリの安全なリンク保護は、電子メール メッセージ内のリンクではなく、Office ドキュメント内のリンクをチェックします (ただし、ドキュメントを開いた後、電子メール メッセージ内の添付された Office ドキュメント内のリンクをチェックできます)。

Office 365 アプリの安全なリンク保護には、次のクライアント要件があります。

- Microsoft 365 Apps または Microsoft 365 Business Premium。
  - Windows、Mac、または Web ブラウザーの Word、Excel、PowerPoint の現在のバージョン。
  - Office iOS または Android デバイス上のアプリをサポートします。
  - Windows 上の Visio。
  - Web ブラウザーの OneNote。

- Office 365 アプリは、最新の認証を使用するように構成されています。 詳細については、「Office 2013、Office [2016、および Office 2019](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)クライアント アプリでのOffice方法を参照してください。

- ユーザーは、自分の仕事用アカウントまたは学校アカウントを使用してサインインします。 詳細については、「サインインしてサインイン[する」をOffice。](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)

365 アプリの安全Office保護は、安全なリンク ポリシーではなく、安全なリンクのグローバル設定で構成します。 ただし、Office 365 アプリの安全なリンク保護を適用するには、Office ドキュメントを開いてリンクをクリックするユーザーをアクティブな安全なリンク ポリシーに含める必要があります。

365 アプリでは、次の安全Office設定を使用できます。

- **Office 365** アプリケーション: サポートされている 365 アプリで安全なリンクOffice有効または無効にします。 既定値と推奨値はオン **です**。

- **[** 安全なリンク] をクリックしても追跡しない : デスクトップ バージョンの Word、Excel、PowerPoint、および Visio でクリックされた URL の安全なリンク のクリック データの保存を有効または無効にします。 推奨値は **[オフ]** です。つまり、ユーザーのクリックが追跡されます。

- **元** の URL への安全なリンクをユーザーがクリックで許可しない : ユーザーが [](#warning-pages-from-safe-links)警告ページをクリックして、デスクトップ バージョンの Word、Excel、PowerPoint、および Visio の元の URL に移動したりブロックしたりします。 既定値と推奨値はオン **です**。

Office 365 アプリの安全なリンクの設定を構成するには、「Office [365](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center)アプリの安全なリンク保護を構成する」を参照してください。

Standard および Strict ポリシー設定の推奨値の詳細については、「安全なリンクのグローバル設定」を [参照してください](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links)。

### <a name="how-safe-links-works-in-office-365-apps"></a>Office 365 アプリでの安全なリンクのしくみ

大まかには、365 アプリの URL に対する安全なリンク保護Office示します。 サポートされている 365 Officeについては、前のセクションで説明します。

1. ユーザーは、Microsoft 365 Apps または Microsoft 365 Business Premium を含む組織内の自分の仕事用アカウントまたは学校アカウントを使用してサインインします。

2. ユーザーは、サポートされているアプリでドキュメントのリンクOffice開いてクリックOfficeします。

3. 安全なリンクは、対象の Web サイトを開く前に URL をすぐに確認します。

   - 安全なリンクのスキャンをスキップする URL がリストに含まれている場合([次の URL をブロックする] ボックスの一覧)、ブロックされた URL の警告ページ[が](#blocked-url-warning)開きます。

   - URL が悪意のあると判断された Web サイトをポイントすると、[](#malicious-website-warning)悪意のある Web サイトの警告ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し示し、ユーザーに適用される安全なリンク ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (疑わしいリンクやファイルを指すリンクをリアルタイムで **URL** スキャンを適用する)、ダウンロード可能なファイルがチェックされます。

   - URL が安全であると見なされた場合、ユーザーは Web サイトにアクセスされます。

   - 安全なリンクのスキャンを完了できない場合、安全なリンクの保護はトリガーできません。 デスクトップ Officeでは、ユーザーは移動先の Web サイトに進む前に警告を受け取る必要があります。

> [!NOTE]
> 各セッションの開始時に、ユーザーが安全なリンクを有効にOfficeがあります。

## <a name="block-the-following-urls-list-for-safe-links"></a>「安全なリンク」の「次の URL をブロックする」の一覧

[ **次の URL をブロック** する] ボックスの一覧では、次の場所にある安全なリンクのスキャンによって常にブロックされるリンクを定義します。

- 電子メール メッセージ
- Windows と Mac Office 365 アプリのドキュメント。
- iOS および Android Officeのドキュメント。

アクティブな安全なリンク ポリシーのユーザーが、サポートされているアプリでブロックされたリンクをクリックすると、[ブロックする URL] 警告ページ [に移動](#blocked-url-warning) します。

安全なリンクのグローバル設定で URL の一覧を構成します。 手順については、「次の URL [をブロックする」の一覧を構成するを参照してください](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center)。

**注**:

- すべての場所でブロックされている URL の本当に汎用的なリストについては、「テナントの許可/ブロックリストの管理 [」を参照してください](tenant-allow-block-list.md)。

- 制限:
  - エントリの最大数は 500 です。
  - エントリの最大長は 128 文字です。
  - すべてのエントリが 10,000 文字を超えることはできません。

- URL の末尾にスラッシュ ( `/` ) を含めない。 たとえば、使用します。 `https://www.contoso.com` 使用することはできません `https://www.contoso.com/` 。

- ドメイン専用 URL (たとえば、または) は、ドメインを含む `contoso.com` `tailspintoys.com` URL をブロックします。

- 完全なドメインをブロックすることなく、サブドメインをブロックできます。 たとえば、サブドメインを含むすべての URL をブロックしますが、完全なドメインを含む `toys.contoso.com*` URL はブロックします `contoso.com` 。

- URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>[次の URL をブロックする] リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

****

|値|結果|
|---|---|
|`contoso.com` <p> または <p> `*contoso.com*`|ドメイン、サブドメイン、およびパスをブロックします。 たとえば、ブロック `https://www.contoso.com` `https://sub.contoso.com` `https://contoso.com/abc` されます。|
|`https://contoso.com/a`|ブロック `https://contoso.com/a` しますが、次のような追加のサブパスはブロックしない `https://contoso.com/a/b` 。|
|`https://contoso.com/a*`|ブロック `https://contoso.com/a` および追加のサブパス 。 `https://contoso.com/a/b`|
|`https://toys.contoso.com*`|サブドメイン (この例では) をブロックしますが、他のドメイン URL (たとえば) へのクリック `toys` を `https://contoso.com` 許可します `https://home.contoso.com` 。|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>「安全なリンク」ポリシーの「次の URL を書き換えない」

> [!NOTE]
> 組織で安全なリンク ポリシーを使用している場合、サード パーティ製のフィッシング テストでサポートされている唯一の方法は、次の **URL** リストを書き換えない方法です。

各安全なリンク ポリシーには、安全なリンクのスキャンによって書き換えされない URL を指定するために使用できる次の URL リストを書き換えないリストが含まれます。 つまり、ポリシーに含まれるユーザーは、安全なリンクによってブロックされる指定された URL にアクセスできます。 安全なリンク ポリシーごとに異なるリストを構成できます。 ポリシー処理は、最初の (最も高い優先度の) ポリシーがユーザーに適用された後に停止します。 したがって、次の URL **リストを** 書き換えないのは 1 つのみ、複数のアクティブな安全なリンク ポリシーに含まれるユーザーに適用されます。

新規または既存の安全なリンク ポリシーの一覧にエントリを追加するには、「[](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies)安全なリンク ポリシーを作成する」または「安全なリンク のポリシーを変更する[」を参照してください](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies)。

**注**:

- 次のクライアントは、安全なリンク ポリシー内の次の **URL** リストを書き換えないことを認識しません。 ポリシーに含まれるユーザーは、次のクライアントでの安全なリンクスキャンの結果に基づいて URL へのアクセスをブロックできます。

  - Microsoft Teams
  - Office Web アプリ

  すべての場所で許可されている URL の本当に汎用的な一覧については、「テナントの許可/ブロックリストの管理 [」を参照してください](tenant-allow-block-list.md)。

- ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加する方法を検討してください。 たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。

- 安全なリンク ポリシーで次の **URL** エントリを既に書き換えない場合は、リストを確認し、必要に応じてワイルドカードを追加してください。 たとえば、リストには次のようなエントリが含まれるので、後で次のような `https://contoso.com/a` サブパスを含めることにします `https://contoso.com/a/b` 。 新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、新しいエントリが `https://contoso.com/a/*` 作成されます。

- URL エントリごとに最大 3 つのワイルドカード ( `*` ) を含めできます。 ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。 たとえば、ユーザーが指定したドメイン内のサブドメインとパスにアクセスできるエントリは、同じ `contoso.com` `*.contoso.com/*` `*.contoso.com/*` ではありません。

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"次の URL を書き換えない" リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

****

|値|結果|
|---|---|
|`contoso.com`|サブドメインまたは `https://contoso.com` パスへのアクセスを許可しますが、アクセスは許可しない。|
|`*.contoso.com/*`|ドメイン、サブドメイン、およびパス (たとえば、, , , , ) へのアクセス `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` を許可します `https://www.contoso.com/a` 。 <p> このエントリは、不正な可能性のあるサイト (以下のように) を許可しないので、本質的に `*contoso.com*` 優れたエントリ `https://www.falsecontoso.com` です。 `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|サブパスへの `https://contoso.com/a` アクセスを許可しますが、次のようなサブパスは許可しない `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|アクセスを許可 `https://contoso.com/a` し、次のようなサブパスを許可します。 `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>安全なリンクからの警告ページ

このセクションでは、URL をクリックすると安全なリンク保護によってトリガーされるさまざまな警告ページの例を示します。

いくつかの警告ページが更新されています。 更新されたページが表示されていない場合は、間もなく表示されます。 更新されたページには、新しい配色、詳細、および指定された警告や推奨事項にもかかわらずサイトに進む機能が含まれます。

### <a name="scan-in-progress-notification"></a>進行中の通知をスキャンする

クリックされた URL は安全なリンクによってスキャンされています。 リンクを再び試す前に、しばらく待つ必要がある場合があります。

!["リンクがスキャンされています" という通知](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

元の通知ページは次のように表示されます。

![元の "リンクがスキャンされています" という通知](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>不審なメッセージの警告

クリックされた URL は、他の疑わしいメッセージに似た電子メール メッセージに含まれます。 サイトに進む前に、電子メール メッセージをもう一度確認することをお勧めします。

!["疑わしいメッセージからリンクがクリックされました" という警告](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>フィッシングの試行に関する警告

クリックされた URL は、フィッシング攻撃として識別された電子メール メッセージに含めでした。 その結果、電子メール メッセージ内のすべての URL がブロックされます。 サイトに進めはお勧めしません。

!["フィッシング メッセージからリンクがクリックされました" という警告](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>悪意のある Web サイトの警告

クリックされた URL は、悪意のあるサイトとして識別されたサイトを示しています。 サイトに進めはお勧めしません。

!["この Web サイトは悪意のある Web サイトとして分類されます" という警告](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

元の警告ページは次のように表示されました。

![元の "この Web サイトは悪意のある Web サイトとして分類されています" という警告](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>ブロックされた URL の警告

クリックされた URL は、組織内の管理者によって手動でブロックされています ([安全なリンク] のグローバル設定の [次の URL をブロックする] の一覧)。  リンクは手動でブロックされたため、安全なリンクによってスキャンされません。

管理者が特定の URL を手動でブロックする理由は複数あります。 サイトをブロックしない場合は、管理者にお問い合わせください。

!["この Web サイトは管理者によってブロックされました" という警告](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

元の警告ページは次のように表示されました。

![元の "この Web サイトは組織の URL ポリシーに対してブロックされました" という警告](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>エラー警告

何らかのエラーが発生し、URL を開くことができません。

!["アクセスしようとしているページを読み込めそうにできません" という警告](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

元の警告ページは次のように表示されました。

![元の "この Web ページを読み込めそうにできません" という警告](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
