---
title: '[リンクセーフの概要を完了Microsoft Defender for Office 365'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.date: 09/08/2021
ms.localizationpriority: medium
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
description: 悪意のある URL をセーフするフィッシングDefender for Office 365攻撃から組織を保護するための、セーフリンク保護について学習します。 [Teams セーフリンク] を見て、リンク メッセージのセーフを参照してください。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11c22239a34b731b57a8730ad1bf03d764ebb106
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507211"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>セーフのリンクMicrosoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用している場合に、Outlook の Safelinks に関する情報を探している場合は、「Advanced [Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

セーフ リンクは[、Defender for Office 365](defender-for-office-365.md) の機能で、メール フロー内の受信メール メッセージの URL のスキャンと書き換え、電子メール メッセージなどの URL とリンクのクリック時の検証を提供します。 セーフリンクスキャンは、受信メール メッセージ (EOP) のスパム[](anti-spam-and-anti-malware-protection.md)対策およびマルウェア対策保護に加えてExchange Online Protectionされます。 安全なリンクのスキャンは、フィッシングやその他の攻撃で使用される悪意のあるリンクから組織を保護できます。

安全なリンクの保護機能は以下の場所で利用できます。

- **電子** メール メッセージ: 既定の セーフ リンク ポリシーは使用されませんが、組み込みの保護プリセット セキュリティ ポリシーは、すべての受信者 (カスタム セーフ リンク ポリシーで定義されていないユーザー) に セーフ リンク保護を提供します。 詳細については、「EOP および EOP のセキュリティ ポリシーを事前に設定[する」を参照Microsoft Defender for Office 365](preset-security-policies.md)。 また、特定のユーザーセーフドメインに適用されるリンク ポリシーを作成できます。 手順については、「セーフ[のリンク ポリシーを設定する」を参照Microsoft Defender for Office 365](set-up-safe-links-policies.md)。

  電子メール メッセージのリンク保護セーフ詳細については、この記事の「セーフのリンク[設定](#safe-links-settings-for-email-messages)」セクションを参照してください。
  
  > [!NOTE]
  > セーフメールが有効なパブリック フォルダーでは、リンクは機能しません。
  >
  > セーフリンクは HTTP(S) 形式と FTP 形式のみをサポートします。

- **Microsoft Teams**: Teams の会話、グループ チャット、またはチャネルからのリンクに対する安全なリンク保護も、安全なリンク ポリシーで制御されます。

  セーフ のリンク保護の詳細Teams、この記事の「セーフ リンク[Microsoft Teams設定」](#safe-links-settings-for-microsoft-teams)を参照してください。

- **Office 365 アプリ**: Office 365 アプリの安全なリンク保護は、サポートされたデスクトップ、モバイル、および Web アプリで利用できます。 リンク **ポリシーセーフ** 外Office 365グローバル設定で、アプリのリンク保護を構成セーフします。 手順については、「グループリンクの[グローバル設定を構成セーフリンクの設定」を参照Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)。

  Office 365 アプリ向けの安全なリンクの保護は、Microsoft Defender for Office 365 のライセンスを付与された組織内のすべてのユーザーに適用され、そのユーザーがアクティブな安全なリンク ポリシーに含まれているかどうかは関係ありません。

  Office 365 アプリの セーフ リンク保護の詳細については、この記事セーフ「Office 365 リンクの設定[](#safe-links-settings-for-office-365-apps)」セクションを参照してください。

この記事では、リンク設定の次の種類のセーフ説明します。

- **設定リンク** ポリシーセーフ: これらの設定は、特定のポリシーに含まれているユーザーにのみ適用され、ポリシー間で設定が異なる場合があります。 これには、以下の設定が含まれます。

  - [セーフメール メッセージのリンク設定](#safe-links-settings-for-email-messages)
  - [セーフのリンク設定Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - [リンク ポリシーの 「次の URL を書き換セーフしない」](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **グローバル セーフ リンクの設定**: これらの設定は、リンク ポリシーではなく、グローバルセーフ構成されます。 これには、以下の設定が含まれます。

  - [セーフアプリの [リンク] Office 365設定](#safe-links-settings-for-office-365-apps)
  - [リンクの [次の URL をブロックする] セーフします。](#block-the-following-urls-list-for-safe-links)

次の表では、Microsoft 365 および Office 365 組織で Defender for Office 365 を含む セーフ リンクのシナリオについて説明します (この例では、ライセンスの不足は決して問題ではありません)。

|シナリオ|結果|
|---|---|
|Jean はマーケティング部門のメンバーです。 セーフ Office 365 アプリのリンク保護は セーフ リンクのグローバル設定で有効にされ、マーケティング部門のメンバーに適用される セーフ リンク ポリシーが存在します。 Jean は、PowerPointメッセージでプレゼンテーションを開き、プレゼンテーション内の URL をクリックします。|Jean は、リンクによってセーフされます。 <p> Jean はリンク ポリシーセーフ含まれており、セーフアプリのリンクOffice 365保護が有効です。 <p> Office 365 アプリの セーフ リンク保護の要件の詳細については、この記事の後半の「セーフ リンク設定 for [Office 365 apps](#safe-links-settings-for-office-365-apps)」セクションを参照してください。|
|Chris の組織Microsoft 365 E5リンク ポリシーセーフ構成されていません。 Chris は、最終的にクリックする悪意のある Web サイトへの URL を含む外部送信者からメールを受信します。|Chris は、リンクによってセーフされません。 <p> 管理者は、受信電子メール メッセージで セーフリンク保護を取得するために、セーフリンク ポリシーを少なくとも 1 つ作成する必要があります。 Chris をポリシーの条件に含め、リンクの保護をセーフ必要があります。|
|Pat の組織では、管理者は セーフ リンク ポリシーを作成したが、セーフ アプリの Office 365保護が有効になっている。 Pat は Word ドキュメントを開き、ファイル内の URL をクリックします。|Pat はリンクによってセーフされません。 <p> セーフ Office 365 アプリのリンク保護はグローバルに有効になりますが、Pat はアクティブな セーフ リンク ポリシーには含まれていないので、保護を適用できます。|
|Lee の組織では、`https://tailspintoys.com`リンクのグローバル設定の [次の **URL** をブロックする] セーフされます。 Lee セーフを含むリンク ポリシーが既に存在します。 Lee は URL を含む電子メール メッセージを受信します `https://tailspintoys.com/aboutus/trythispage`。 Lee が URL をクリックします。|Lee の URL が自動的にブロックされる場合があります。リスト内の URL エントリと、使用するメール クライアント Lee によって異なります。 詳細については、この記事の後半の「リンク」セクションの「セーフ [URL を](#block-the-following-urls-list-for-safe-links)ブロックする」を参照してください。|
|Jamie と Julia は両方とも、contoso.com。 一昔前に、管理者は jamie と Julia の両方にセーフリンク ポリシーを構成していました。 Jamie は、電子メールに悪意のある URL が含まれていることを知らずに、電子メールを Julia に送信します。|Julia は、内部受信者セーフメッセージに適用セーフリンク ポリシーが構成されている場合は、セーフ リンクによって保護されます。 詳細については、この記事の[「セーフのリンク](#safe-links-settings-for-email-messages)設定」セクションを参照してください。|

## <a name="safe-links-settings-for-email-messages"></a>セーフメール メッセージのリンク設定

安全なリンクは、受信メールをスキャンして、悪意のあるハイパーリンクを検出します。 スキャンされた URL は、Microsoft 標準 URL プレフィックスを使用して書き換えされます。 `https://nam01.safelinks.protection.outlook.com` リンクを書き換えた後、潜在的な悪意のあるコンテンツがないか分析します。

[セーフリンクは URL を書き換えた後、メッセージが手動で転送または返信された場合でも  (内部受信者と外部受信者の両方に) 書き換えたままです。 転送メッセージまたは返信先メッセージに追加された追加のリンクは書き換えされません。 ただし、受信トレイ ルールまたは  SMTP 転送による自動転送の場合、その受信者が セーフ リンクによって保護されている場合や、以前の通信で URL が既に書き換え済みである場合を含め、最終的な受信者を対象としたメッセージに URL は書き換えされません。 リンクが有効セーフ限り、URL は書き換えたかどうかに関係なく、配信前にスキャンされます。 アンラップされた URL は、デスクトップ バージョン 16.0.12513 以降の Outlook のクリック時に セーフ Links へのクライアント側 API 呼び出しによってもチェックされます。

電子メール メッセージにセーフリンク ポリシーの設定については、次の一覧で説明します。

- **On: セーフ リンク** は、ユーザーがメール内のリンクをクリックすると、既知の悪意のあるリンクの一覧をチェックします。電子メール メッセージでリンクのスキャンを有効またはセーフ無効にします。 推奨される値が選択され (オン)、次のアクションが実行されます。
  - セーフリンクスキャニングは、Outlook (C2R) で有効Windows。
  - URL は書き換え、ユーザーはメッセージ内の URL をクリックセーフリンク保護を介してルーティングされます。
  - クリックすると、既知の悪意のある URL の一覧と [次の URL をブロックする] リストに対して [URL がチェックされます](#block-the-following-urls-list-for-safe-links)。
  - 有効な評価を持つ URL は、バックグラウンドで非同期的に無効になります。

  次の設定は、電子メール メッセージセーフリンクスキャンがオンの場合にのみ使用できます。

  - **[セーフ** 組織内で送信された電子メール メッセージへのリンクの適用: 同じ組織内の内部送信者と内部受信者の間で送信されたメッセージに対する セーフ Exchange Online リンクのスキャンを有効または無効にします。 推奨される値が選択されています (オン)。

  - **ファイルを指** す疑わしいリンクやリンクのリアルタイム URL スキャンを適用する: ダウンロード可能なコンテンツを指す電子メール メッセージ内のリンクを含む、リンクのリアルタイム スキャンを有効にします。 推奨される値が選択されています (オン)。

  - **メッセージを配信する前に URL のスキャンが完了するのを待ちます**。
    - 選択済み (オン): URL を含むメッセージは、スキャンが完了するまで保持されます。 メッセージは、URL が安全と確認された後にのみ配信されます。 これは推奨される値です。
    - 選択されていない (オフ): URL スキャンを完了できない場合は、メッセージを配信します。

  - **URL を書き換えないで、SafeLinks API** を使用してチェックを行います。この設定が有効になっている場合、URL の折り返しは行なされません。 セーフリンクは、URL クリック時に API を介して排他的に呼び出され、それをサポートするOutlookによって呼び出されます。 推奨値は無効です。

- **ユーザークリックの追跡**: 電子メール メッセージでクリックセーフ URL のリンク クリック データの保存を有効または無効にします。 推奨値は、この設定を選択したままにすること (ユーザーのクリックを追跡する) です。

  内部送信者と内部受信者の間で送信される電子メール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。

- **ユーザーに元の URL への** クリックを許可する: ユーザーが警告ページをクリックして [](#warning-pages-from-safe-links)元の URL をクリックしたりブロックしたりします。 推奨値は無効です。

- **通知ページと警告ページに組織** のブランドを表示する: このオプションは、警告ページに組織のブランド化を表示します。 ブランド化は、既定の Microsoft 警告ページが攻撃者によって頻繁に使用されるので、ユーザーが正当な警告を識別するのに役立ちます。 カスタマイズされたブランド化の詳細については、「組織のカスタマイズ [Microsoft 365テーマ」を参照してください](../../admin/setup/customize-your-organization-theme.md)。

  [リンク] ポリシーの Standard および Strict ポリシー設定の推奨値のセーフ詳細については、「セーフリンク ポリシー設定」[を参照してください](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)。

- **受信者フィルター**: ポリシーが適用されるユーザーを決定する受信者の条件と例外を指定する必要があります。 条件や例外には次のプロパティを使用できます。
  - **受信者が次の場合**
  - **受信者ドメインは、**
  - **受信者が次のメンバーの場合**

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

- **優先度**: 複数のポリシーを作成する場合は、適用する順序を指定できます。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

  優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。
  
### <a name="how-safe-links-works-in-email-messages"></a>電子メール セーフリンクの動作方法

電子メール メッセージ内の URL に対するリンクセーフの仕組みについて、大まかに説明します。

1. メッセージが受信者のメールボックスに配信される前に、すべての電子メールは EOP を通過します。ここで、インターネット プロトコル (IP) およびエンベロープ フィルター、署名ベースのマルウェア保護、スパム対策およびマルウェア対策フィルター。

2. ユーザーは自分のメールボックスでメッセージを開き、メッセージ内の URL をクリックします。

3. セーフリンクは、Web サイトを開く前に URL をすぐに確認します。

   - URL が [次の URL をブロックする] リストに **含** まれている場合は、 [ブロックされた URL 警告が開](#blocked-url-warning) きます。

   - URL が悪意のあると判断された Web サイトを参照している場合は、悪意[](#malicious-website-warning)のある Web サイトの警告ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し示し、[ファイルをポイントする疑わしいリンクとリンクのリアルタイム **URL** スキャンを適用する] 設定が、ユーザーに適用されるポリシーで有効になっている場合、ダウンロード可能なファイルがチェックされます。

   - URL が安全と判断された場合、Web サイトが開きます。

## <a name="safe-links-settings-for-microsoft-teams"></a>セーフのリンク設定Microsoft Teams

リンクポリシーで、セーフのリンク保護を有効またはMicrosoft Teams無効セーフします。 具体的には、[不明な URL または悪意のある可能性のある URL に対してアクションを選択する **] Microsoft Teams** します。 推奨される値は **On です**。

> [!NOTE]
> Teams セーフ のリンク保護を有効またはオフにTeams、変更が有効になるには最大 24 時間かかる場合があります。

電子メール メッセージ内のリンクセーフ適用されるリンク ポリシーの次の設定は、メール メッセージ内のリンクにも適用Teams。

- **ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する**
- **ユーザーのクリックを追跡しない**
- **ユーザーに元の URL へのクリックを許可しない**

これらの設定については、「電子メール メッセージセーフ[リンクの設定」で説明しました](#safe-links-settings-for-email-messages)。

Microsoft Teams の セーフ リンク保護を有効にすると、保護されたユーザーがリンクをクリックすると、Teams の URL が既知の悪意のあるリンクの一覧に対してチェックされます (クリック時の保護)。 URL は書き換え用ではありません。 リンクが悪意のあると判明した場合、ユーザーには次のエクスペリエンスがあります。

- Teams 会話、グループ チャット、またはチャネルからリンクがクリックされた場合、次のスクリーンショットに示すように警告ページが既定の Web ブラウザーに表示されます。
- リンクがピン留めされたタブからクリックされた場合、警告ページは、そのタブ内Teamsインターフェイスに表示されます。Web ブラウザーでリンクを開くオプションは、セキュリティ上の理由から無効になっています。
- ポリシーの [ユーザーによる元の URL へのクリックを許可しない] 設定の構成方法に応じて、ユーザーは元の **URL** (スクリーンショットの [続行] (推奨しない **)** をクリックするかしないかによって異なる場合があります。 ユーザーが元の URL をクリックできない場合は、[ユーザーが元の **URL** をクリックすることを許可しない] 設定を有効にすることをお勧めします。

Teams 保護が有効になっている セーフ Links ポリシーにリンクを送信したユーザーが含まれていない場合、ユーザーはコンピューターまたはデバイスの元の URL を自由にクリックできます。

:::image type="content" source="../../media/tp-safe-links-for-teams-malicious.png" alt-text="悪意セーフを報告Teamsページのリンク" lightbox="../../media/tp-safe-links-for-teams-malicious.png":::

警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。 ただし、元のリンクを再度クリックすると、セーフリンクが再スキャンされますので、警告ページが再表示されます。

### <a name="how-safe-links-works-in-teams"></a>[セーフリンクの動作Teams

高レベルでは、次に示すのは、セーフリンク保護の URL に対する機能Microsoft Teams。

1. ユーザーがアプリのTeamsします。

2. Microsoft 365の組織に Microsoft Defender for Office 365 が含まれており、ユーザーがアクティブな セーフ リンク ポリシーに含まれていて、Microsoft Teams の保護が有効になっているか確認します。

3. URL は、チャット、グループ チャット、チャネル、およびタブ内のユーザーのクリック時に検証されます。

## <a name="safe-links-settings-for-office-365-apps"></a>セーフアプリの [リンク] Office 365設定

セーフ Office 365 アプリのリンク保護は、電子メール メッセージ内のリンクではなく Office ドキュメント内のリンクをチェックします (ただし、ドキュメントを開いた後、添付された Office ドキュメント内のリンクを電子メール メッセージでチェックできます)。

セーフアプリのリンク保護Office 365クライアント要件は次のとおりです。

- Microsoft 365 AppsまたはMicrosoft 365 Business Premium。
  - 現在のバージョンの Word、Excel、PowerPoint、Windows Web ブラウザーで使用できます。
  - Office Android デバイス上のアプリを使用します。
  - VisioのWindows。
  - OneNoteブラウザーで使用します。
  - Outlook EML Windows MSG ファイルを開く際に、このファイルを使用します。

- Office 365は、モダン認証を使用するように構成されています。 詳細については、「[Office 2013、Office 2016、および Office 2019](../../enterprise/modern-auth-for-office-2013-and-2016.md) クライアント アプリの最新の認証のしくみ」を参照してください。

- ユーザーは、自分の仕事または学校のアカウントを使用してサインインします。 詳細については、「サインインしてサインイン[する」を参照Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)。

リンクポリシーセーフではなく、Office 365 セーフ リンクのグローバル設定で、セーフ セーフ リンク保護を構成します。 この保護は、ユーザーがアクティブな セーフ Links ポリシーに含まれているかどうかに関係なく、Defender for Office 365 のライセンスを取得している組織内のすべてのユーザーに適用されます。

[リンク] セーフは、アプリで使用できるOffice 365示します。

- **Office 365:** サポートされているアプリでセーフリンクスキャンを有効またはOffice 365します。 既定値と推奨値は **[オン] です**。

- **ユーザーが [セーフ** リンク] をクリックした場合は追跡しない: デスクトップ バージョンの Word、Excel、PowerPoint、および Visio でクリックされた URL の セーフ リンク クリック データの保存を有効または無効にします。 推奨される値は **Off** です。つまり、ユーザーのクリックが追跡されます。

- ユーザーが元の **URL** への安全なリンクをクリックさせない: ユーザーが警告ページをクリックして [](#warning-pages-from-safe-links)デスクトップ バージョンの Word、Excel、PowerPoint、および Visio の元の URL をクリックVisio。 既定値と推奨値は **[オン] です**。

アプリの [リンクセーフ] 設定を構成するには、「Office 365アプリのリンク保護セーフ[構成する」をOffice 365してください](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal)。

Standard および Strict ポリシー設定の推奨値の詳細については、「グローバル設定 for セーフ[リンク」を参照してください](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)。

### <a name="how-safe-links-works-in-office-365-apps"></a>アプリセーフリンクの動作Office 365方法

高レベルでは、アプリ内の URL に対セーフリンク保護の仕組Office 365示します。 サポートされているアプリOffice 365前のセクションで説明します。

1. ユーザーは、組織で自分の仕事または学校のアカウントを使用してサインインします。Microsoft 365 AppsまたはMicrosoft 365 Business Premium。

2. ユーザーが開き、サポートされているドキュメント内OfficeリンクをクリックOffice アプリ。

3. セーフリンクは、ターゲット Web サイトを開く前に URL をすぐに確認します。

   - リンクのスキャンをスキップする URL セーフリストに含まれている場合は、ブロックされた URL 警告ページ[が開](#blocked-url-warning)きます。

   - URL が悪意のあると判断された Web サイトを参照している場合は、悪意[](#malicious-website-warning)のある Web サイトの警告ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し示し、ユーザーに適用される セーフ Links ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (ファイルを指す疑わしいリンクやリンクに対してリアルタイム **URL** スキャンを適用する) 場合、ダウンロード可能なファイルがチェックされます。

   - URL が安全であると見なされた場合、ユーザーは Web サイトにアクセスされます。

   - リンクセーフが完了しない場合、リンクセーフ保護はトリガーされない。 デスクトップ Officeでは、ユーザーが宛先 Web サイトに進む前に警告が表示されます。

> [!NOTE]
> 各セッションの開始時に、ユーザーが [リンク] を有効にセーフには数秒かかるOfficeがあります。

## <a name="block-the-following-urls-list-for-safe-links"></a>リンクの [次の URL をブロックする] セーフします。

[**次の URL をブロックする**] ボックスの一覧では、次の場所にある [リンクセーフによって常にブロックされるリンクを定義します。

- 電子メール メッセージ
- ドキュメントと Mac Office 365アプリWindowsドキュメント。
- iOS Office Android 用のドキュメント。

アクティブなリンク ポリシーのユーザーセーフサポートされているアプリのブロックされたリンクをクリックすると、[ブロックされた URL の警告] [ページに移動](#blocked-url-warning)します。

リンクのグローバル設定で URL の一覧を構成セーフします。 手順については、「次の [URL をブロックする」リストを構成するを参照してください](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal)。

**注**:

- あらゆる場所でブロックされている URL の本当に汎用的なリストについては、「 [Manage the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。
- [次の URL を **ブロックする] リストの制限** 。
  - エントリの最大数は 500 です。
  - エントリの最大長は 128 文字です。
  - すべてのエントリは、10,000 文字を超えることはできません。
- URL の末尾にスラッシュ (`/`) を含めない。 たとえば、 を使用します`https://www.contoso.com``https://www.contoso.com/`。
- ドメイン専用 URL (`contoso.com``tailspintoys.com`たとえば、または) は、ドメインを含むすべての URL をブロックします。
- 完全なドメインをブロックせずにサブドメインをブロックできます。 たとえば、サブ `toys.contoso.com*` ドメインを含む URL をブロックしますが、完全なドメインを含む URL はブロックしない `contoso.com`。
- URL エントリごとに最大 3 つのワイルドカード (`*`) を含めできます。

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>"次の URL をブロックする" リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

|値|結果|
|---|---|
|`contoso.com` <p> または <p> `*contoso.com*`|ドメイン、サブドメイン、およびパスをブロックします。 たとえば、、`https://www.contoso.com``https://sub.contoso.com`、および`https://contoso.com/abc`ブロックされます。|
|`https://contoso.com/a`|ブロック `https://contoso.com/a` ですが、追加のサブパスはブロックしない `https://contoso.com/a/b`。|
|`https://contoso.com/a*`|ブロック`https://contoso.com/a`や追加のサブパス (.`https://contoso.com/a/b`|
|`https://toys.contoso.com*`|サブドメイン (この例では`toys` ) をブロックしますが、他のドメイン URL (など) へのクリックを許可 `https://contoso.com` します `https://home.contoso.com`。|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>リンク ポリシーの 「次の URL を書き換セーフしない」

> [!NOTE]
> 組織で [リンク] セーフを使用している場合は、サード パーティのフィッシング テストでサポートされている唯一の方法は、次の **URL** リストを書き換えない方法です。

各 セーフ リンク ポリシーには、次の URL を書き換えないリストが含まれます。このリストを使用して、リンクスキャンによって書き換えされない URL をセーフできます。 つまり、ポリシーに含まれるユーザーは、ポリシーに含まれているユーザーが、リンクによってブロックされる指定された URL にアクセスセーフします。 リンク ポリシーごとに異なるリストセーフ構成できます。 ポリシー処理は、最初の (優先度が最も高い) ポリシーがユーザーに適用された後に停止します。 そのため、1 つの **み次の URL** リストを書き換えないと、複数のアクティブ なリンク ポリシーに含まれるユーザーセーフ適用されます。

新規または既存の セーフ リンク ポリシーのリストにエントリを追加するには、「[セーフ リンク](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) ポリシーの作成」または「セーフ [リンク ポリシーの変更」を参照](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-modify-safe-links-policies)してください。

**注**:

- 次のクライアントは、[リンク] ポリシーの [次の **URL** を書き換セーフしません。 ポリシーに含まれるユーザーは、次のクライアントで [リンク] スキャンの結果に基セーフ URL へのアクセスをブロックできます。
  - Microsoft Teams
  - Office Web アプリ

  すべての場所で許可されている URL の本当に汎用的なリストについては、「Manage [the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。 ただし、追加された URL は セーフ Links ポリシーで行う必要があるので、セーフ セーフ リンクの書き換えから除外されません。

- ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加する方法を検討してください。 たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。
- 既に [セーフ  リンク] ポリシーで次の URL エントリを書き換えない場合は、リストを確認し、必要に応じてワイルドカードを追加してください。 たとえば、リストには次のような `https://contoso.com/a` エントリが含まれるので、後で次のようなサブパスを含めることにしました `https://contoso.com/a/b`。 新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、 になります `https://contoso.com/a/*`。
- URL エントリごとに最大 3 つのワイルドカード (`*`) を含めできます。 ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。 たとえば、指定したドメイン`contoso.com``*.contoso.com/*``*.contoso.com/*`内のサブドメインとパスをユーザーがアクセスできるので、エントリは同じではありません。
- URL で HTTP から HTTPS への自動リダイレクト (302 リダイレクトなど) を使用し、同じ URL の HTTP エントリと HTTPS エントリの両方をリストに入力すると、2 `http://www.contoso.com` `https://www.contoso.com`番目の URL エントリが最初の URL エントリに置き換わる可能性があります。 この動作は、HTTP バージョンと HTTPS バージョンの URL が完全に分離されている場合は発生しません。
- HTTP バージョンと HTTPS http:// を https://(つまり、contoso.com) を指定しない。
- `*.contoso.com` 指定 **したドメイン** contoso.com 子ドメインの両方をカバーするには、両方を除外する必要があります。
- `contoso.com/*`カバー **は** contoso.com ので、両方を除外する必要`contoso.com``contoso.com/*`はありません。ただ`contoso.com/*`十分です。
- ドメインのすべての反復を除外するには、2 つの除外エントリが必要です。 `contoso.com/*` と `*.contoso.com/*`. これらを組み合わせて HTTP と HTTPS の両方、メイン ドメイン contoso.com と子ドメイン、および終了部分 (たとえば、contoso.com と contoso.com/vdir1 の両方が対象) を除外します。

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>"次の URL を書き換えない" リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

|値|結果|
|---|---|
|`contoso.com`|サブドメインまたは `https://contoso.com` パスへのアクセスを許可しますが、アクセスを許可しない。|
|`*.contoso.com/*`|ドメイン、サブドメイン、およびパス (`https://www.contoso.com``https://www.contoso.com`たとえば、) へのアクセスを`https://maps.contoso.com`許可します`https://www.contoso.com/a`。 <p> このエントリは、潜在的 `*contoso.com*`に詐欺的なサイトを許可しないので、本来よりも優れた方法です `https://www.falsecontoso.com` 。 `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|サブパスへのアクセス `https://contoso.com/a`を許可しますが、サブパスは許可しない `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|次のようなアクセスと `https://contoso.com/a` サブパスを許可します `https://contoso.com/a/b`|

## <a name="warning-pages-from-safe-links"></a>[リンク] からのセーフページ

このセクションには、URL をクリックするときにリンク保護を実行セーフさまざまな警告ページの例を示します。

いくつかの警告ページが更新された点に注意してください。 更新されたページがまだ表示されていない場合は、すぐに表示されます。 更新されたページには、新しい配色、詳細、および指定された警告と推奨事項にもかかわらずサイトに進む機能が含まれます。

### <a name="scan-in-progress-notification"></a>進行中の通知をスキャンする

クリックされた URL は[リンク] でセーフされます。 リンクを再度試す前に、しばらく待つ必要がある場合があります。

:::image type="content" source="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png" alt-text="リンクがスキャンされているという通知" lightbox="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png":::

元の通知ページは次のように表示されます。

:::image type="content" source="../../media/04368763-763f-43d6-94a4-a48291d36893.png" alt-text="リンクがスキャン中の通知" lightbox="../../media/04368763-763f-43d6-94a4-a48291d36893.png":::

### <a name="suspicious-message-warning"></a>疑わしいメッセージの警告

クリックされた URL は、他の疑わしいメッセージに似た電子メール メッセージに含まれます。 サイトに進む前に、電子メール メッセージをもう一度確認することをお勧めします。

:::image type="content" source="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png" alt-text="疑わしいメッセージ警告からリンクがクリックされた" lightbox="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png":::

### <a name="phishing-attempt-warning"></a>フィッシングの試行の警告

クリックされた URL は、フィッシング攻撃として識別された電子メール メッセージに含めでした。 その結果、電子メール メッセージ内のすべての URL がブロックされます。 サイトに進むのはやめすることをお勧めします。

:::image type="content" source="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png" alt-text="フィッシング メッセージからリンクがクリックされたという警告" lightbox="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png":::

### <a name="malicious-website-warning"></a>悪意のある Web サイトの警告

クリックされた URL は、悪意のあるサイトをポイントします。 サイトに進むのはやめすることをお勧めします。

:::image type="content" source="../../media/058883c8-23f0-4672-9c1c-66b084796177.png" alt-text="Web サイトが悪意のある Web サイトとして分類されているという警告" lightbox="../../media/058883c8-23f0-4672-9c1c-66b084796177.png":::

元の警告ページは次のように表示されます。

:::image type="content" source="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png" alt-text="Web サイトが悪意のある Web サイトとして分類されているという元の警告" lightbox="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png":::

### <a name="blocked-url-warning"></a>ブロックされた URL の警告

クリックされた URL は、組織内の管理者によって手動でブロックされています ([リンク]  のグローバル設定の [次の URL をブロックセーフします)。 リンクは手動でブロックセーフリンクによってスキャンされません。

管理者が特定の URL を手動でブロックする理由は複数あります。 サイトをブロックしない場合は、管理者に問い合わせください。

:::image type="content" source="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png" alt-text="Web サイトが管理者によってブロックされたという警告" lightbox="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png":::

元の警告ページは次のように表示されます。

:::image type="content" source="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png" alt-text="組織の URL ポリシーごとに Web サイトがブロックされたという元の警告" lightbox="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png":::

### <a name="error-warning"></a>エラー警告

何らかのエラーが発生し、URL を開くことができません。

:::image type="content" source="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png" alt-text="アクセスしようとしているページが読み込めなことを示す警告" lightbox="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png":::

元の警告ページは次のように表示されます。

:::image type="content" source="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png" alt-text="Web ページを読み込めなかせたという警告" lightbox="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png":::
