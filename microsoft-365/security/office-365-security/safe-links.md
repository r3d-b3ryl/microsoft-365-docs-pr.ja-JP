---
title: Microsoft Defender for Office 365 の完全な安全なリンクの概要
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
description: 悪意のある URL を使用するフィッシングやその他の攻撃から組織を保護するための Defender for Office 365 の安全なリンク保護について説明します。 Teams の安全なリンクを見つけ、安全なリンク メッセージのグラフィックを表示します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 27c9f6c36959394eadea727e81fe0dde35e66993
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66943935"
---
# <a name="safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の安全なリンク

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をお持ちの法人のお客様を対象としています。Outlook.com、Microsoft 365 ファミリー、または Microsoft 365 Personal を使用していて、Outlook のセーフリンクに関する情報を探している場合は、「[高度な Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」 を参照してください。

安全なリンクは、[Defender for Office 365](defender-for-office-365.md) の機能で、メール フロー内の受信メール メッセージの URL スキャンと書き換え、メール メッセージなどに含まれる URL やリンクの Time-of-Click 検証を行います。 安全なリンクのスキャンは、Exchange Online Protection (EOP) の受信メール メッセージにおける通常の[スパム対策](anti-spam-protection.md)と[マルウェア対策](anti-malware-protection.md)に追加して発生します。 安全なリンクのスキャンは、フィッシングやその他の攻撃で使用される悪意のあるリンクから組織を保護できます。

Microsoft Defender for Office 365 のセーフ リンクを使用して悪意のあるリンクから保護する方法について、この短いビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGzjb]

> [!NOTE]
> 既定のセーフ リンク ポリシーはありませんが、事前設定された **組み込みの保護** セキュリティ ポリシーにはサポートされている Office アプリ内のメール メッセージ、Microsoft Teams、ファイルに、Defender for Office 365 のライセンスを取得しているすべての受信者 (カスタム セーフ リンク ポリシー、標準セキュリティ ポリシー、厳密な事前設定セキュリティ ポリシーで定義されていないユーザー) 用の安全なリンク保護があります。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。 また、特定のユーザー、グループ、またはドメインに適用される安全なリンクポリシーを作成することもできます。 手順については、「[Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。

安全なリンクの保護機能は以下の場所で利用できます。

- **メール メッセージ**: メール メッセージ内のリンクに対する安全なリンク保護は、安全なリンク ポリシーで制御されます。

  メール メッセージの安全なリンク保護の詳細については、この記事で後述する「[電子メール メッセージの安全なリンク設定](#safe-links-settings-for-email-messages)」セクションを参照してください。

  > [!NOTE]
  > 安全なリンクは、メールが有効なパブリック フォルダーでは機能しません。
  >
  > 安全なリンクでは、HTTP 形式と FTP 形式のみがサポートされます。

- **Microsoft Teams**: Teams の会話、グループ チャット、またはチャネルからのリンクに対する安全なリンク保護は、安全なリンク ポリシーで制御されます。

  Teams の安全なリンク保護の詳細については、この記事で後述する「[Microsoft Teams の安全なリンク設定](#safe-links-settings-for-microsoft-teams)」セクションを参照してください。

  > [!NOTE]
  > 現在、Microsoft Teams のセーフ リンク保護は、Microsoft 365 GCC High または Microsoft 365 DoD では使用できません。

- **Office アプリ**: サポートされている Office デスクトップ、モバイル、Web アプリの安全なリンク保護は、安全なリンク ポリシーによって制御されます。

  Office アプリの安全なリンク保護の詳細については、この記事で後述する「[Office アプリの安全なリンク設定](#safe-links-settings-for-office-apps)」セクションを参照してください。

この記事には、次の種類の安全なリンク設定の詳細な説明が含まれています。

- **安全なリンク ポリシーの設定**: これらの設定は、特定のポリシーに含まれているユーザーにのみ適用され、ポリシー間で設定が異なる場合があります。これらの設定には以下が含まれます:

  - [メール メッセージの安全なリンク設定](#safe-links-settings-for-email-messages)
  - [Microsoft Teams の安全なリンク設定](#safe-links-settings-for-microsoft-teams)
  - [Office アプリの安全なリンク設定](#safe-links-settings-for-office-apps)
  - [安全なリンクポリシーの「次のURLを書き換えないでください」リスト](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **グローバル セーフ リンク設定**: これらの設定は、安全なリンク ポリシーではなく、グローバルに構成されます。これらの設定には以下が含まれます:

  - [安全なリンクの「次のURLをブロックする」リスト](#block-the-following-urls-list-for-safe-links)

次の表では、Defender for Office 365 を含む Microsoft 365および Office 365 組織の安全なリンクのシナリオについて説明します (ライセンスの不足は、この例では問題になることはありません)。

|シナリオ|結果|
|---|---|
|Jean は、マーケティング部門のメンバーです。 Office アプリの安全なリンク保護が、マーケティング部門のメンバーに適用される安全なリンク ポリシーで有効になっています。 メール メッセージで [PowerPoint プレゼンテーション] を開き、[プレゼンテーションの URL] をクリックします。|Safe は安全なリンクによって保護されています。 <p> Jean は安全なリンク ポリシーに含まれており、そこでは Office アプリの安全なリンク保護が有効になっています。 <p> Office アプリの安全なリンク保護の要件の詳細については、この記事で後述する「Office アプリの [安全なリンクの設定](#safe-links-settings-for-office-apps)」セクションを参照してください。|
|Chris の Microsoft 365 E5 組織には、安全なリンク ポリシーが構成されていません。 Chris は、悪意のある Web サイトへの URL を含む外部送信者から、最終的にクリックしたメールを受信します。|Chris は安全なリンクによって保護されています。 <p> 事前設定された **組み込みの保護** セキュリティ ポリシーには、すべての受信者 (カスタム セーフ リンク ポリシー、標準セキュリティ ポリシー、厳密な事前設定セキュリティ ポリシーで定義されていないユーザー) 用の安全なリンク保護があります。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。|
|Pat の組織では管理者が Pat に適用する安全なリンク ポリシーを作成していますが、Office アプリの安全なリンク保護が無効になっています。 Pat が Word 文書を開き、ファイル内の URL をクリックします。|Pat は安全なリンクで保護されていません。 <p> Pat はアクティブな安全なリンク ポリシーに含まれていますが、そのポリシーでは Office アプリの安全なリンク保護が無効になっているため、保護は適用されません。|
|Lee の組織では、`https://tailspintoys.com`は安全なリンクのグローバル設定の **[次の URL をブロックする]** のリストで構成さています。 Lee を含む安全なリンク ポリシーは既に存在します。 Lee は、URL `https://tailspintoys.com/aboutus/trythispage`を含むメール メッセージを受信します。 Lee はリンクをクリックします。|URL は Lee に対して自動的にブロックされる可能性があります。これは、リスト内の URL エントリと Lee が使用したメール クライアントによって異なります。 詳細については、この記事で後述する[安全なリンクの 「次の URL をブロックする」](#block-the-following-urls-list-for-safe-links)リスト セクションを参照してください。|
|Jamie と Julia はどちらも contoso.com で働いています。 以前、管理者は Jamie と Julia の両方に適用される安全なリンク ポリシーを構成しました。 Jamie は、メールに悪意のある URL が含まれていることを知らずに、Julia にメールを送信します。|自分に適用される安全なリンク ポリシーが、内部受信者間のメッセージに適用されるように構成されている **場合**、Julia は安全なリンクによって保護されています。 詳細については、この記事で後述する「[メール メッセージの安全なリンク設定](#safe-links-settings-for-email-messages)」セクションを参照してください。|

## <a name="recipient-filters-in-safe-links-policies"></a>安全なリンク ポリシーの受信者フィルター

ポリシーの適用先を決定する受信者の条件と例外を指定する必要があります。条件や例外には次のプロパティを使用できます。 条件や例外には次のプロパティを使用できます。

- **受信者が次の場合**
- **受信者のドメインは次のとおりです。**
- **受信者が次のメンバーの場合**

条件または例外は 1 回だけ使用できますが、条件または例外には複数の値を含めることができます。同じ条件または例外に複数の値がある場合、OR ロジック (_\<recipient1\>_ または _\<recipient2\>_ など) が用されます。別の条件や例外がある場合は、AND ロジック (_\<recipient1\>_ や _\<member of group 1\>_ など) が適用されます。

> [!IMPORTANT]
> 複数の異なる条件または例外は可算的ではありません。包括的です。 ポリシーは、指定された _すべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
>
> - 受信者は次のとおりです: romain@contoso.com
> - 受信者が次のメンバーの場合: Executive
>
> ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
>
> 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

## <a name="safe-links-settings-for-email-messages"></a>メール メッセージの安全なリンク設定

安全なリンクは、受信メールをスキャンして、悪意のあるハイパーリンクを検出します。 スキャンされた URL は、Microsoft 標準 URL プレフィックス (`https://nam01.safelinks.protection.outlook.com`) を使用して書き換えられているか、_ラップされます_。 リンクを書き換えた後、潜在的な悪意のあるコンテンツがないか分析します。

安全なリンクが URL を書き換えた後も、メッセージが(内部受信者と外部受信者の両方に)_手動_ で転送または返信されても、URLは書き換えられたままになります。 転送されたメッセージまたは返信先メッセージに追加された追加のリンクは書き換えられません。

受信トレイ ルールによる _自動_ 転送、または SMTP による転送の場合、次のいずれかのステートメントに該当しない _限り_、最終的な受信者に向けたメッセージで URL が書き換えられることはありません。

- 受信者は、安全なリンクでも保護されます。
- URL は、以前の通信で既に書き換えられました。

安全なリンク保護が有効になっている限り、URL が書き換えられたかどうかに関係なく、メッセージ配信前にスキャンされます。 サポートされているバージョンの Outlook (Outlook for Desktop バージョン 16.0.12513 以降) では、ラップされていない URL は、クリックしたときに、安全なリンクへのクライアント側の API 呼び出しによってもチェックされます。

メール メッセージに適用される安全なリンク ポリシーの設定については、次のリストを参照してください。

- **オン: 安全なリンクは、ユーザーがメール内のリンクをクリックしたときに、既知の悪意のあるリンクのリストを確認します**: メール メッセージでの安全なリンクのスキャンを有効または無効にします。 推奨値は選択 (オン) で、次のアクションが実行されます。
  - Windows の Outlook (C2R) で安全なリンクのスキャンが有効になっています。
  - URL は書き換えられ、ユーザーがメッセージ内の URL をクリックすると、安全なリンク保護によってルーティングされます。
  - クリックすると、既知の悪意のある URL のリストと [[次の URL をブロックする] リスト](#block-the-following-urls-list-for-safe-links) に対して URL がチェックされます。
  - 有効な評価が指定されていない URL は、バックグラウンドで非同期に生成されます。

  次の設定は、安全なリンクのスキャンがメール メッセージ内で有効になっている場合にのみ使用できます。

  - **組織内で送信されるメール メッセージに安全なリンクを適用します**: 同じ Exchange Online 組織内の内部送信者と内部受信者の間で送信されるメッセージに対する安全なリンクのスキャンを有効または無効にします。 推奨値は選択 (オン) です。

  - **疑わしいリンクやファイルを指すリンクのリアルタイム URL スキャンを適用します**: ダウンロード可能なコンテンツを指しているメール メッセージ内のリンクなど、リンクのリアルタイム スキャンを有効にします。 推奨値は選択 (オン) です。

    - **URL スキャンが完了するまで待ち、その後でメッセージを配信します**: 
      - 選択 (オン): URL を含むメッセージは、スキャンが完了するまで保持されます。 メッセージは、URL が安全であることが確認された後にのみ配信されます。 これは推奨値です。
      - 未選択 (オフ): URL スキャンを完了できない場合には、メッセージが配信されます。

  - **URL を書き換えず、SafeLinks API のみを使用してチェックを行います**: この設定が選択されていると、URL ラッピングは行われません。 サポートされているバージョンの Outlook (Outlook for Desktop バージョン 16.0.12513 以降) では、URL をクリックすると、API を介して安全なリンクが排他的に呼び出されます。

  安全なリンク ポリシーの標準および厳格なポリシー設定の推奨値の詳細については、「[セーフ リンク ポリシーの設定](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)」を参照してください。

### <a name="how-safe-links-works-in-email-messages"></a>メール メッセージでの安全なリンクのしくみ

高レベルでは、メール メッセージ内の URL に対する安全なリンク保護は次のように機能します。

1. すべてのメールは EOP を通過します。この EOP では、メッセージが受信者のメールボックスに配信される前に、インターネット プロトコル (IP) とエンベロープ フィルター、署名ベースのマルウェア対策、スパム対策、マルウェア対策フィルターが適用されます。

2. ユーザーはメールボックスでメッセージを開き、メッセージ内の URL をクリックします。

3. 安全なリンクは、Web サイトを開く前に URL をすぐに確認します。

   - URL が **次の URL をブロックする** リストに含まれている場合は、[ブロックされた URL の警告](#blocked-url-warning) が開きます。

   - URL が悪意のある Web サイトを指している場合、[悪意のある Web サイトの警告](#malicious-website-warning) ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指し、**不審なリンクや、ファイルを指しているリンクに対してリアルタイム URL スキャンを適用する** 設定がユーザーに適用されるポリシーで有効になっている場合、ダウンロード可能なファイルがチェックされます。

   - URL が安全であると判断された場合は、その Web サイトが開きます。

## <a name="safe-links-settings-for-microsoft-teams"></a>Microsoft Teams の安全なリンク設定

安全なリンク ポリシーで Microsoft Teams の安全なリンク保護を有効または無効にします。 特別に、**オン: 安全なリンクは、ユーザーが Microsoft Teams でリンクをクリックしたときに、既知の悪意のあるリンクのリストを確認する** 設定を使用します。 推奨される値はオン (選択) です。

> [!NOTE]
> Teams の安全なリンク保護をオンまたはオフにすると、変更が有効になるまでに最大 24 時間かかる場合があります。
>
> 現在、Microsoft Teams のセーフ リンク保護は、Microsoft 365 GCC High または Microsoft 365 DoD では使用できません。

Microsoft Teams の安全なリンク保護を有効にすると、保護されたユーザーがリンク (クリック時の保護) をクリックしたときに、Teams の URL が既知の悪意のあるリンクのリストに対してチェックされます。 URL は書き換えされません。 悪意のあるリンクが見つかった場合、ユーザーは次のエクスペリエンスを利用できます。

- Teams の会話、グループ チャット、またはチャネルからリンクがクリックされた場合は、次のスクリーンショットに示すように、既定の Web ブラウザーに警告ページが表示されます。
- ピン留めされたタブからリンクをクリックすると、そのタブ内の Teams インターフェイスに警告ページが表示されます。セキュリティ上の理由から、Web ブラウザーでリンクを開くオプションは無効になっています。
- ポリシーにある **[ユーザーが元の URL へクリック スルーするのを許可する]** 設定の構成に応じて、元の URL へのクリック スルーが許可されたり、または許可されなくなります (**[続行する(推奨されません)]** のスクリーンショット)。 **[ユーザーが元の URL へクリック スルーするのを許可する]** 設定を有効にすることをお勧めします。

リンクを送信したユーザーは Teams 保護が有効になっている安全なリンク ポリシーで保護されていない場合、自分のコンピューターまたはデバイス上の元の URL を自由にクリック スルーすることができます。

:::image type="content" source="../../media/tp-safe-links-for-teams-malicious.png" alt-text="悪意のあるリンクを報告する Teams の [安全なリンク] ページ。" lightbox="../../media/tp-safe-links-for-teams-malicious.png":::

Web ページ警告ページの **[戻る** ] ボタンをクリックすると、ユーザーは元のコンテキストまたは URL の場所に戻ります。 ただし、元のリンクをもう一度クリックすると、安全なリンクによって URL が再スキャンされるため、警告ページが再表示されます。

### <a name="how-safe-links-works-in-teams"></a>Teams での安全なリンクのしくみ

高レベルでは、Microsoft Teams の URL に対する安全なリンク保護は次のように機能します。

1. ユーザーが Teams アプリを起動します。

2. Microsoft 365 は、ユーザーの組織に Microsoft Defender for Office 365 が含まれていること、およびユーザーが Microsoft Teams の保護が有効になっているアクティブな安全なリンク ポリシーに含まれていることを確認します。

3. URL は、チャット、グループ チャット、チャネル、タブでユーザーのクリック時に検証されます。

## <a name="safe-links-settings-for-office-apps"></a>Office アプリの安全なリンク設定

Office アプリの安全なリンク保護では、メール メッセージ内のリンクではなく、Office ドキュメント内のリンクがチェックされます。 ただし、ドキュメントを開いた後は、メール メッセージ内の添付 Office ドキュメントのリンクを確認できます。

安全なリンク ポリシーで Office アプリの安全なリンク保護を有効または無効にします。 特別に、**オン: 安全なリンクは、ユーザーが Microsoft Office アプリでリンクをクリックしたときに、既知の悪意のあるリンクのリストを確認する** 設定を使用します。 推奨される値はオン (選択) です。

Office アプリの安全なリンク保護には、次のクライアント要件があります。

- Microsoft 365 アプリまたは Microsoft 365 Business Premium。
  - Windows、Mac、または Web ブラウザーでの Word、Excel、PowerPoint の現在のバージョン。
  - iOS または Android デバイス上の Office アプリ。
  - Windows 上の Visio。
  - Web ブラウザーでの OneNote。
  - 保存されたEMLまたはMSGファイルを開くときのWindows 用Outlook。

- Office アプリは、先進認証を使用するように構成されています。 詳細については、[「Office 2013、Office 2016、Office 2019 クライアント アプリでの先進認証のしくみ](../../enterprise/modern-auth-for-office-2013-and-2016.md)」を参照してください。

- ユーザーは職場または学校のアカウントを使用してサインインします。 詳細については、「[Office へのサインイン](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)」を参照してください。

標準および厳格ポリシー設定の推奨値の詳細については、「[安全なリンクのグローバル設定](recommended-settings-for-eop-and-office365.md#global-settings-for-safe-links)」参照してください。

### <a name="how-safe-links-works-in-office-apps"></a>Office アプリでの安全なリンクのしくみ

高レベルでは、Office アプリの URL に対する安全なリンク保護は次のように機能します。 サポートされている Office アプリについては、前のセクションで説明されています。

1. ユーザーは、Microsoft 365 Apps または Microsoft 365 Business Premium を含む組織内の職場または学校アカウントを使用してサインインします。

2. ユーザーは、サポートされている Office アプリで Office ドキュメントのリンクを開いてクリックします。

3. 安全なリンクは、ターゲット Web サイトを開く前に URL をすぐに確認します。

   - URL が安全なリンクのスキャンをスキップするリスト (**[次の URL をブロックする]** リスト) に含まれている場合、[[ブロックされた URL 警告]](#blocked-url-warning) ページが開きます。

   - URL が悪意のある Web サイトを指している場合、[悪意のある Web サイトの警告](#malicious-website-warning) ページ (または別の警告ページ) が開きます。

   - URL がダウンロード可能なファイルを指しており、ユーザーに適用される安全なリンク ポリシーがダウンロード可能なコンテンツへのリンクをスキャンするように構成されている場合 (**ファイルを指す疑わしいリンクとリンクをリアルタイムで URL スキャンする**)、ダウンロード可能なファイルがチェックされます。

   - URL が安全と見なされると、Web サイトに移動します。

   - 安全なリンクのスキャンを完了できない場合、安全なリンクの保護はトリガーされません。 Office デスクトップ クライアントでは、移行先の Web サイトに進む前に、ユーザーに警告が表示されます。

> [!NOTE]
> Office アプリの安全なリンクが利用できることを確認するため、各セッションの開始時で数秒かかる場合があります。

## <a name="click-protection-settings-in-safe-links-policies"></a>安全なリンク ポリシーで保護の設定をクリックする

これらの設定は、メール、Teams、Office アプリの安全なリンクに適用されます。

- **ユーザーのクリックを追跡する**: クリックされた URL の安全なリンク クリック データの保存を有効または無効にします。 この設定はオンのままにすることをお勧めします。

  Office アプリの安全なリンクでは、この設定はデスクトップ バージョンの Word、Excel、PowerPoint、Visio に適用されます。

  内部送信者と内部受信者の間で送信されるメール メッセージ内のリンクの URL クリック追跡は、現在サポートされていません。

  この設定を選択すると、以下の設定が使用できます。

  - **ユーザーが元の URL へクリック スルーするのを許可する** - [警告ページ](#warning-pages-from-safe-links) から元の URL へのクリックをユーザーに許可または禁止します。 推奨値が選択されていません (オフ)。

    Office アプリの安全なリンクでは、この設定はデスクトップ バージョンの Word、Excel、PowerPoint、Visio で元の URL に適用されます。

  - **組織のブランディングを通知と警告のページに表示します**: このオプションは、組織のブランドを警告ページに表示します。 ブランド化は、ユーザーが正当な警告を識別するのに役立ちます。これは、既定の Microsoft 警告ページが攻撃者によってよく使用されるためです。 カスタマイズされたブランド化の詳細については、「[組織で使用する Microsoft 365 のテーマをカスタマイズする](../../admin/setup/customize-your-organization-theme.md)」を参照してください。

## <a name="priority-of-safe-links-policies"></a>安全なリンク ポリシーの優先度

複数のポリシーを作成した後、適用する順序を指定できます。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。 **組み込みの保護** ポリシーは常に最後に適用されます。 事前設定された **標準** セキュリティ ポリシーおよび **厳格** セキュリティ ポリシーに関連付けられている安全なリンク ポリシーは、常にカスタムセーフ リンク ポリシーの前に適用されます。

優先順位と複数のポリシーの評価と適用方法の詳細については、「[事前設定されたセキュリティ ポリシーとその他のポリシーの優先順位](preset-security-policies.md#order-of-precedence-for-preset-security-policies-and-other-policies)」と「[メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

## <a name="block-the-following-urls-list-for-safe-links"></a>安全なリンクの [次の URL をブロックする] リスト

> [!NOTE]
> [テナント許可/ブロック リスト](allow-block-urls.md#create-block-url-entries-in-the-tenant-allowblock-list) で URL エントリのブロックを管理できるようになりました。 "次の URL をブロックする"リストは非推奨のプロセスです。 既存のエントリを "次の URL をブロックする" リストから移行し、テナント許可/ブロック リストの URL エントリをブロックします。 ブロックされた URL を含むメッセージは検疫されます。

**[次の URL をブロックする]** のリストでは、次の場所で安全なリンク スキャンによって常にブロックされるリンクを定義します。

- 電子メール メッセージ
- Windows および Mac の Office アプリのドキュメント。
- Office for iOS および Android のドキュメント。

アクティブな安全なリンク ポリシーのユーザーがサポートされているアプリでブロックされたリンクをクリックすると、[[ブロックされた URL の警告]](#blocked-url-warning) ページに移動します。

[安全なリンクのグローバル設定]で URL のリストを構成します。 手順については、「[[次の URL をブロックする] リストを構成する](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal)」を参照してください。

**注意**:

- すべての場所でブロックされている URL の真のユニバーサル リストについては「[テナントの許可/禁止リストを管理する](tenant-allow-block-list.md)」を参照してください。
- **[次の URL をブロックする]** の制限:
  - エントリの最大数は 500 です。
  - エントリの最大長は 128 文字です。
  - すべてのエントリは 10,000 文字以下にする必要があります。
- URL の最後にスラッシュ (`/`) を含めないでください。たとえば、`https://www.contoso.com/` ではなく、`https://www.contoso.com` を使用します。
- ドメイン専用 URL (`contoso.com` または `tailspintoys.com` など) は、ドメインを含む URL をブロックします。
- サブドメインは、フルドメインをブロックせずにブロックできます。 たとえば、`toys.contoso.com*` はサブドメインを含む URL をブロックしますが、フルドメイン `contoso.com` を含む URL はブロックしません。
- URL エントリごとに最大 3 つのワイルドカード (`*`) を含めることができます。

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>[次の URL をブロックする] リストのエントリ構文

入力できる値とその結果の例を次の表に示します。

|値|結果|
|---|---|
|`contoso.com` <p> or <p> `*contoso.com*`|ドメイン、サブドメイン、パスをブロックします。 たとえば、`https://www.contoso.com`、`https://sub.contoso.com`、 `https://contoso.com/abc` はブロックされます。|
|`https://contoso.com/a`|`https://contoso.com/a` をブロックしますが、`https://contoso.com/a/b` のような追加のサブパスはブロックしません。|
|`https://contoso.com/a*`|`https://contoso.com/a` や `https://contoso.com/a/b` などの追加のサブパスをブロックします。|
|`https://toys.contoso.com*`|サブドメイン (この例では `toys`) をブロックしますが、他のドメイン URL (`https://contoso.com` や `https://home.contoso.com` など) へのクリックを許可します。|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>安全なリンクポリシーの「次の URL を書き換えない」リスト

> [!NOTE]
> [次の URL を書き換えない] リストのエントリは、メール フロー中に安全なリンクによってスキャンまたはラップされません。 [テナント許可/禁止リストで URL エントリを許可する](allow-block-urls.md#create-allow-url-entries) を使用して、メール フロー _および_ クリック時に安全なリンクで URL がスキャンされたり、ラップされないようにします。

各安全なリンク ポリシーには、**[次の URL を書き換えない]** リストが含まれています。このリストを使用して、安全なリンクのスキャンによって書き換えられない URL を指定できます。 つまり、このリストでは、ポリシーに含まれているユーザーは、安全なリンクによってブロックされる指定された URL にアクセスできます。 さまざまな安全なリンク ポリシーで、異なるリストを構成できます。 ポリシーの処理は、最初の (最も優先度が高い) ポリシーがユーザーに適用された後に停止します。 そのため、複数のアクティブな安全なリンク ポリシーに含まれているユーザーには、「**次の URL を書き換えない**」リストが 1 つだけ適用されます。

新規または既存の安全なリンク ポリシーのリストにエントリを追加するには、「[安全なリンク ポリシーの作成](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)」または「[安全なリンクポリシーの変更](set-up-safe-links-policies.md#use-the-microsoft-365-defender-portal-to-modify-safe-links-policies)」を参照してください。

**注意**:

- 次のクライアントは、安全なリンク ポリシーの 「**次の URL を書き換えない**」のリストを認識しません。 ポリシーに含まれるユーザーは、次のクライアントでの安全なリンク スキャンの結果に基づいて、URL へのアクセスをブロックできます。
  - Microsoft Teams
  - Office Web Apps

  あらゆる場所で許可される URL の真のユニバーサル リストについては「[テナントの許可/禁止リストの管理](tenant-allow-block-list.md)」を参照してください。 ただし、安全なリンク ポリシーで行う必要があるため、そこに追加された URL は安全なリンクの書き換えから除外されないことに注意してください。

- ユーザー エクスペリエンスを向上させるために、一般的に使用される内部 URL をリストに追加することを検討してください。 たとえば、Skype for Business や SharePoint などのオンプレミス サービスがある場合は、それらの URL を追加してスキャンから除外できます。
- 既に「**安全なリンク ポリシーの次の URL を書き換えない**」エントリがある場合は、必ずリストを確認し、必要に応じてワイルドカードを追加してください。 たとえば、リストに `https://contoso.com/a` のようなエントリがあり、後で `https://contoso.com/a/b` のようなサブパスを含めることにしたとします。 新しいエントリを追加する代わりに、既存のエントリにワイルドカードを追加して、`https://contoso.com/a/*` になるようにします。
- URL エントリごとに最大 3 つのワイルドカード (`*`) を含めることができます。 ワイルドカードには、プレフィックスまたはサブドメインが明示的に含まれます。 たとえば、エントリ `contoso.com` は、`*.contoso.com/*` と同じではありません。`*.contoso.com/*` では、ユーザーは指定されたドメイン内のサブドメインとパスにアクセスできます。
- URL で HTTP から HTTPS への自動リダイレクト (たとえば、`http://www.contoso.com` から `https://www.contoso.com` への 302 リダイレクト) を使用し、同じ URL の HTTP エントリと HTTPS エントリの両方をリストに入力しようとすると、2 番目の URL エントリが最初の URL エントリに置き換わる場合があります。この動作は、URL の HTTP バージョンと HTTPS バージョンが完全に分離されている場合には発生しません。
- HTTP バージョンと HTTPS バージョンの両方を除外するために、http:// または https:// (contoso.com) を指定しないでください。
- `*.contoso.com`は、contoso.com をカバー **しない** ので、指定されたドメインと子ドメインの両方をカバーするには両方を除外する必要があります。
- `contoso.com/*`**のみ** contoso.com をカバーしているため、`contoso.com`と`contoso.com/*`の両方を排除する必要はありません。`contoso.com/*`だけで十分です。
- ドメインのすべてのイテレーションを除外するには、`contoso.com/*` と `*.contoso.com/*`、2 つの除外エントリが必要です。これらを組み合わせて、HTTP と HTTPS、メイン ドメイン contoso.com、子ドメイン、および終了部分 (たとえば、contoso.com と contoso.com/vdir1 の両方をカバー) の両方を除外します。

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>「次の URL を書き換えない」のエントリ構文リスト

入力できる値とその結果の例を次の表に示します。

|値|結果|
|---|---|
|`contoso.com`|`https://contoso.com` へのアクセスを許可しますが、サブドメインやパスにはアクセスできません。|
|`*.contoso.com/*`|ドメイン、サブドメイン、パスへのアクセスを許可します (例: `https://www.contoso.com`、 `https://www.contoso.com`、`https://maps.contoso.com`、 `https://www.contoso.com/a`)。 <p> このエントリは、`*contoso.com*` よりも本質的に優れています。これは、`https://www.falsecontoso.com` や `https://www.false.contoso.completelyfalse.com` などの不正なサイトを許可しないためです|
|`https://contoso.com/a`|`https://contoso.com/a`へのアクセスは許可されますが、`https://contoso.com/a/b`のようなサブパスは許可されません|
|`https://contoso.com/a/*`|`https://contoso.com/a` などの`https://contoso.com/a/b`やサブパスへのアクセスを許可します|

## <a name="warning-pages-from-safe-links"></a>安全なリンクからの警告ページ

このセクションには、URL をクリックしたときに安全なリンク保護によってトリガーされるさまざまな警告ページの例が含まれています。

いくつかの警告ページが更新されていることに注意してください。 更新されたページがまだ表示されていない場合は、間もなく表示されます。 更新されたページには、新しい配色、より詳細な色、および特定の警告と推奨事項に関わらずサイトに進む機能が含まれています。

### <a name="scan-in-progress-notification"></a>スキャンが進行中の通知

クリックされた URL は、安全なリンクによってスキャンされています。 リンクを再試行する前に、しばらく待つ必要がある場合があります。

:::image type="content" source="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png" alt-text="リンクがスキャン中の通知" lightbox="../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png":::

元の通知ページは次のようになります。

:::image type="content" source="../../media/04368763-763f-43d6-94a4-a48291d36893.png" alt-text="「リンクをスキャンしています」通知" lightbox="../../media/04368763-763f-43d6-94a4-a48291d36893.png":::

### <a name="suspicious-message-warning"></a>疑わしいメッセージの警告

クリックされた URL は、他の疑わしいメッセージに似たメール メッセージに含まれています。 サイトに進む前に、メール メッセージを再確認することをお勧めします。

:::image type="content" source="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png" alt-text="「疑わしいメッセージのリンクがクリックされました」警告" lightbox="../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png":::

### <a name="phishing-attempt-warning"></a>フィッシング詐欺の試行に関する警告

クリックされた URL は、フィッシング攻撃として識別されたメール メッセージに含まれています。 その結果、メール メッセージ内のすべての URL がブロックされます。 サイトに進まないことをお勧めします。

:::image type="content" source="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png" alt-text="フィッシング メッセージのリンクからクリックされたことを示す警告" lightbox="../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png":::

### <a name="malicious-website-warning"></a>悪意のある Web サイトの警告

クリックされた URL は、悪意のあるサイトを指しています。 サイトに進まないことをお勧めします。

:::image type="content" source="../../media/058883c8-23f0-4672-9c1c-66b084796177.png" alt-text="Web サイトが悪意のあるものとして分類されていることを示す警告" lightbox="../../media/058883c8-23f0-4672-9c1c-66b084796177.png":::

元の警告ページは次のようになります。

:::image type="content" source="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png" alt-text="Web サイトが悪意のあるものとして分類されていることを示す元の警告" lightbox="../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png":::

### <a name="blocked-url-warning"></a>ブロックされた URL の警告

クリックされた URL は、組織内の管理者によって手動でブロックされています (安全なリンクのグローバル設定で「**次の URL をブロック**」のリスト)。 リンクは手動でブロックされたため、安全なリンクによってスキャンされませんでした。

管理者が特定の URL を手動でブロックする理由はいくつかあります。 サイトをブロックすべきでないと思われる場合は、管理者にお問い合わせください。

:::image type="content" source="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png" alt-text="管理者によって Web サイトがブロックされたことを示す警告" lightbox="../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png":::

元の警告ページは次のようになります。

:::image type="content" source="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png" alt-text="組織の URL ポリシーに従って Web サイトがブロックされたことを示す元の警告" lightbox="../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png":::

### <a name="error-warning"></a>エラー警告

何らかのエラーが発生したため、URL を開くことができません。

:::image type="content" source="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png" alt-text="アクセスしようとしているページを読み込めないことを示す警告" lightbox="../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png":::

元の警告ページは次のようになります。

:::image type="content" source="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png" alt-text="Web ページを読み込めなかったことを示す警告" lightbox="../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png":::
