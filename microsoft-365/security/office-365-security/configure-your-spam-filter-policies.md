---
title: スパム フィルター ポリシーの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: 管理者が、Exchange Online Protection (EOP) で迷惑メール対策ポリシーを表示、作成、変更、削除する方法を説明します。
ms.openlocfilehash: 60b53e21978867321f6fe824da35db683dc76663
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372563"
---
# <a name="configure-anti-spam-policies-in-eop"></a>EOP でのスパム対策ポリシーの構成

Exchange Online のメールボックスを使用している Microsoft 365 の組織、または Exchange Online のメールボックスを使用していないもののスタンドアロンの Exchange Online Protection (EOP) をお使いの組織の場合、受信メール メッセージは EOP によってスパムから自動的に保護されます。 EOP では、スパムに対する組織の全体的防御の一環として、スパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれます) を使用します。 詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。

管理者は、既定のスパム対策ポリシーの表示、編集、構成を行うことができます (削除はできません)。 より細かく設定できるように、カスタムのスパム対策保護ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

スパム対策ポリシーの構成は、セキュリティ/コンプライアンス センターで、または PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 の組織向け Exchange Online PowerShell、Exchange Online メールボックスを持たない組織向けのスタンドアロン EOP PowerShell) で行います。

## <a name="anti-spam-policies-in-the-security--compliance-center-vs-powershell"></a>セキュリティ & コンプライアンスセンターと  PowerShell のスパム対策ポリシー

EOP のスパム対策ポリシーの基本的な要素は次のとおりです。

- **スパム フィルター ポリシー**: スパム フィルター判定のアクションと通知オプションを指定します。

- **スパム フィルター ルール**: スパム フィルター ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。

これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターでスパム対策を管理する際には明白ではありませんが、以下の違いがあります。

- セキュリティ/コンプライアンス センターでスパム対策ポリシーを作成する場合、実際にはスパム フィルター ルール、および関連付けられているスパム フィルター ポリシーの両方に同じ名前を使用して同時に作成しています。

- セキュリティ/コンプライアンス センターでスパム対策ポリシーを変更する場合、名前、優先順位、有効/無効の切り替え、そして受信者フィルターに関連する設定の変更は、実際にはスパム フィルター ルールを変更しています。 他のすべての設定は、関連付けられているスパム フィルター ポリシーを変更します。

- セキュリティ/コンプライアンス センターからスパム対策ポリシーを削除すると、スパム フィルター ルールおよび関連付けられたスパム フィルター ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロンの EOP PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの違いは明白です。 スパム フィルター ポリシーは **\*-HostedContentFilterPolicy** コマンドレットを使用して管理し、スパム フィルター ルールは **\*-HostedContentFilterRule** コマンドレットを使用して管理します。

- PowerShell では、最初にスパム フィルター ポリシーを作成し、それからルールが適用されるポリシーを特定するスパム フィルター ルールを作成します。

- PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの設定は別々に変更します。

- PowerShell からスパム フィルター ポリシーを削除しても、対応しているスパム フィルター ルールは自動で削除されず、逆もまた同様です。

### <a name="default-anti-spam-policy"></a>既定のスパム対策ポリシー

各組織には Default という名前の組み込みのスパム対策ポリシーがあり、以下の特徴があります。

- ポリシーに関連付けられているスパム フィルター ルール (受信者フィルター) がない場合でも、Default という名前のスパム フィルター ポリシーは組織内の全受信者に適用されます。

- Default という名前のポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。

- Default という名前のポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

スパム フィルター処理の有効性を高めるために、特定のユーザーまたはユーザー グループに適用される、より厳密な設定を持つカスタムのスパム対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 迷惑メール対策ポリシーを追加、変更、削除するには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 迷惑メール対策ポリシーに読み取り専用でアクセスするには、次のいずれかの役割グループのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- マルウェア対策ポリシーに推奨される設定については、「[EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)」を参照してください。

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>セキュリティ/コンプライアンス センターを使用してスパム対策ポリシーを作成する

セキュリティ/コンプライアンス センターでスパム対策ポリシーを作成する場合、実際にはスパム フィルター ルール、および関連付けられているスパム フィルター ポリシーの両方に同じ名前を使用して同時に作成しています。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[スパム対策の設定]** ページの **[ポリシーの作成]** をクリックします。

3. 開いた **[新しいスパム フィルター ポリシー]** ポップアップで、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。 以下の文字は使用しないでください: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`

      これらの文字が含まれているスパム対策ポリシーを、Exchange 管理センター (EAC) で以前に作成した場合は、PowerShell でそのスパム対策ポリシーの名前を変更する必要があります。 手順については、このトピックで後述する「[PowerShell を使用してスパム フィルター ルールを変更する](#use-powershell-to-modify-spam-filter-rules)」を参照してください。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

4. (オプション) **[迷惑メールおよびバルク メールの処理]** セクションを展開し、以下の設定を確認または構成します。

   - **スパムとバルク メールを受信するためのアクションを選択します**: 以下のスパム対策フィルター判定に基づき、メッセージに対して行うアクションを選択または確認します。

     - **スパム**
     - **高確度迷惑メール**
     - **フィッシング詐欺メール**
     - **高確度フィッシング詐欺メール**
     - **バルク メール**

     次の表で、スパム対策フィルター判定に使用可能なアクションを説明します。

     - チェック マーク ( ![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) は、アクションが使用可能であることを示します (すべてのアクションがすべてのスパム対策フィルター判定に使用できるわけではありません)。
     - チェック マークの後にアスタリスク ( <sup>\*</sup> ) がある場合、スパム対策フィルター判定の既定のアクションであることを示しています。

    |||||||
    |:---|:---:|:---:|:---:|:---:|:---:|
    ||**スパム**|**高<br/>確度<br/>迷惑メール**|**フィッシング詐欺<br/>メール**|**高<br/>確度<br/>フィッシング詐欺<br/>メール**|**バルク<br/> メール**|
    |**メッセージを迷惑メール フォルダーに移動する**: メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1</sup>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
    |**X-ヘッダーを追加する**: X-ヘッダーをメッセージ ヘッダーに追加し、そのメッセージをメールボックスに配信します。 <br/> 後で **[この X ヘッダーのテキストを追加する]** ボックスに、X-ヘッダーのフィールド名 (値ではなく) を入力します。 <br/><br/> **スパム**および**高確度迷惑メール**判定の場合、メッセージは [迷惑メール] フォルダーに移動されます。<sup>1、2</sup>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
    |**件名行の先頭にテキストを追加する**: メッセージの件名行の先頭にテキストを追加します。 メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1、2</sup> <br/> テキストを後で **[件名行の先頭にこのテキストを追加する]** ボックスに入力します。|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**[メッセージをメール アドレスにリダイレクトする]:** メッセージを本来の受信者の代わりに他の受信者に送信します。 <br/> 後で、受信者を **[このメール アドレスにリダイレクトする]** ボックスに指定してください。|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**[メッセージの削除]:** 添付ファイルすべてを含め、メッセージ全体が確認なしで削除されます。|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**[メッセージを隔離する]:** メッセージを本来の受信者に送信せず、検疫に送信します。 <br/> 後で、検疫でメッセージを保持する期間を **[検疫]** ボックスに指定します。|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |**アクションなし**|||||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
    |

    > <sup>1</sup> Exchange Online では、受信トレイで迷惑メール ルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定では有効)。 詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。<br/>EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。<br/><br/><sup>2</sup> この値を、メール フロー ルール (トランスポート ルールとも言う) の条件として、メッセージのフィルター処理やルーティングに使用することができます。

   - **しきい値を選択**: **[バルク メール]** スパム対策フィルター判定に指定されたアクションをトリガーするメッセージの Bulk Complaint Level (BCL) を指定します (アクションは、指定された値以上ではなく、指定された値より大きい場合にトリガーされます)。 値が大きければ大きいほど、そのメッセージの信頼度は低い (迷惑メールである可能性が高い) ことを示します。 既定の値は 7 です。 詳細については、「[EOP の Bulk Complaint Level (BCL)](bulk-complaint-level-values.md)」および「[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。

     既定では、スパム対策ポリシーでの PowerShell のみの設定である _MarkAsSpamBulkMail_ は、`On` です。 この設定は、**バルク メール** フィルター判定の結果に大きく影響します。

     - **_MarkAsSpamBulkMail_ が [On]**: しきい値よりも高い BCL は、フィルター判定「**スパム**」に相当する SCL 6 に変換され、**バルク メール** フィルター判定に指定されたアクションがメッセージに対して実行されます。

     - **_MarkAsSpamBulkMail_ が [Off]**: メッセージには BCL がスタンプされますが、**バルク メール** フィルター判定に対して_何のアクションも実行されません_。 実際には、BCL しきい値と**バルク メール** フィルター判定アクションは無関係です。

   - **検疫**: スパム対策フィルター判定のアクションとして **[メッセージを検疫]** を選択した場合に、メッセージを検疫に保持する期間を指定します。 期間が終了すると、メッセージは削除されます。 既定値は 30 日です。 有効な値は 1 日から 30 日です。 検疫の詳細については、以下のトピックを参照してください。

     - [EOP で隔離されたメッセージ](quarantine-email-messages.md)
     - [EOP の管理者として検疫済みメッセージとファイルを管理する](manage-quarantined-messages-and-files.md)
     - [EOP のユーザーとして検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)

   - **この X-ヘッダー テキストを追加する**: このボックスは、**[X-ヘッダーの追加]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。 指定する値は、メッセージ ヘッダーに追加されるヘッダー フィールドの*名前*です。 ヘッダー フィールドの*値*は常に `This message appears to be spam` です。

     最大の長さは 255 文字で、値にスペースやコロン (:) を含めることはできません。

     たとえば、値 `X-This-is-my-custom-header` を入力すると、メッセージに追加される X-ヘッダーは `X-This-is-my-custom-header: This message appears to be spam.` です。

     スペースまたはコロン (:) を含む値を入力した場合、入力した値は無視され、既定の X-ヘッダー (`X-This-Is-Spam: This message appears to be spam.`) がメッセージに追加されます。

   - **件名行の先頭にこのテキストを追加する**: このボックスは、**[件名行の先頭にテキストを追加する]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。 メッセージの件名行の先頭に追加するテキストを入力します。

   - **このメール アドレスにリダイレクトする**: このボックスは、**[メール アドレスにリダイレクトする]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。 メッセージの配信先のメール アドレスを入力します。 複数の値をセミコロン (;) で区切って入力できます。

   - **安全性のヒント**: 既定で [安全性のヒント] は有効になっていますが、これらは **オン**になっているチェックボックスをオフにすることで無効にできます。 安全性のヒントの詳細については、「[メール メッセージの安全性のヒント](safety-tips-in-office-365.md)」を参照してください。

   **[ゼロアワー自動消去]** 設定: Exchange Online のメールボックスに既に配信されたメッセージを ZAP が検出し、アクションを実行します。 ZAP の詳細については、「[ゼロアワー自動消去 - スパムまたはマルウェアからの保護](zero-hour-auto-purge.md)」を参照してください。

   - **Spam ZAP**: 既定では、ZAP はスパム検出に対して有効になっていますが、**オン**になっているチェックボックスをオフにすることで無効にできます。

   - **フィッシング詐欺に対する ZAP**: 既定では、ZAP はフィッシング検出に対して有効になっていますが、**オン**になっているチェックボックスをオフにすることで無効にできます。

5. (オプション) **[受信許可一覧]** セクションを展開すると、スパム対策フィルター処理をスキップできるメッセージ送信者を、メール アドレスごと、またはメール ドメインごとに構成できます。

   > [!CAUTION]
   > • その場合、ドメインを追加する前に慎重に検討してください。 詳細については、「[EOP での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。 <br/><br/> • 承認済みドメイン (自分が所有しているドメイン) や一般的なドメイン (microsoft.com や office.com など) は、決して、許可するドメインのリストに追加しないでください。 そのようにすると、攻撃者は組織にスパム フィルターをバイパスするメールを送信できるようになります。

   - **受信許可**: **[編集]** をクリックします。 表示される **[許可された送信者一覧]** ポップアップで、以下の手順を実行します。

      a. 送信者の電子メール アドレスを入力します。 複数のメール アドレスをセミコロン (;) で区切って指定できます。

      b. Click ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) をクリックして送信者を追加します。

      必要な回数だけこれらの手順を繰り返します。

      追加した送信者が、ポップアップの **[受信許可送信者]** セクションに表示されます。 送信者を削除するには、![[削除] アイコン](../../media/scc-remove-icon.png)をクリックします。

      完了したら、**[保存]** をクリックします。

   - **ドメインを許可**: **[編集]** をクリックします。 表示される **[許可されているドメイン一覧]** ポップアップで、以下の手順を実行します。

      a. ドメインを入力します。 複数のドメインをセミコロン (;) で区切って指定できます。

      b. Click ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) をクリックしてドメインを追加します。

      必要な回数だけこれらの手順を繰り返します。

      追加したドメインが、ポップアップの **[受信許可ドメイン]** セクションに表示されます。 ドメインを削除するには、![[削除] アイコン](../../media/scc-remove-icon.png)をクリックします。

      完了したら、**[保存]** をクリックします。

6. (オプション) **[受信拒否一覧]** セクションを展開すると、常に高確度迷惑メールとマークされるメッセージ送信者をメール アドレスごと、またはメール ドメインごとに構成できます。

   > [!NOTE]
   > 手動でのドメインの受信拒否は危険ではありませんが、管理作業の負荷が増大する可能性があります。 詳細については、「[EOP での受信拒否リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。

   - **受信拒否**: **[編集]** をクリックします。 表示される **[受信拒否リスト一覧]** で、以下の手順を実行します。

      a. 送信者の電子メール アドレスを入力します。 複数のメール アドレスをセミコロン (;) で区切って指定できます。 ワイルドカード (*) は使用できません。

      b. Click ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) をクリックして送信者を追加します。

      必要な回数だけこれらの手順を繰り返します。

      追加した送信者が、ポップアップの **[ブロックする差出人]** セクションに表示されます。 送信者を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。

      完了したら、**[保存]** をクリックします。

   - **ドメインをブロック**: **[編集]** をクリックします。 表示される **[ブロックされたドメイン一覧]** ポップアップで、以下の手順を実行します。

      a. ドメインを入力します。 複数のドメインをセミコロン (;) で区切って指定できます。 ワイルドカード (*) は使用できません。

      b. Click ![[追加] アイコン](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) をクリックしてドメインを追加します。

      必要な回数だけこれらの手順を繰り返します。

      追加したドメインが、ポップアップの **[ブロックされたドメイン]** リストに表示されます。 ドメインを削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。

      完了したら、**[保存]** をクリックします。

7. (オプション) **[海外からの迷惑メール]** セクションを展開すると、スパム対策フィルター処理によってブロックされる電子メールの言語や発信国を設定できます。

   - **次の言語で書かれたメール メッセージをフィルターします**: この設定は既定では無効になっています (**状態: OFF**)。 **[編集]** をクリックします。 表示される **[海外からの迷惑メールの設定]** ポップアップで、次の設定を構成します。

     - **次の言語で書かれたメール メッセージをフィルターします**: この設定を有効にするには、チェックボックスをオンにします。 この設定を無効にするには、チェック ボックスをオフにします。

     - ボックス内をクリックし、言語の*名前*の入力を始めます。 フィルター処理の対象となる、サポートされている言語のリストが、対応する ISO 639-2 の言語コードと共に表示されます。 探している言語が見つかったら、それを選択します。 必要な回数だけこの手順を繰り返します。

       選択した言語のリストがポップアップに表示されます。 言語を削除するには、 ![[削除] ボタンをクリックします](../../media/scc-remove-icon.png)。

     完了したら、**[保存]** をクリックします。

   - **次の国または地域から送信されたメール メッセージをフィルターします**: この設定は、既定では無効になっています (**状態: OFF**)。 有効にするには、**[編集]** をクリックします。 表示される **[海外からの迷惑メールの設定]** ポップアップで、次の設定を構成します。

     - **次の国または地域から送信されたメール メッセージをフィルターします**: この設定を有効にするには、チェックボックスをオンにします。 この設定を無効にするには、チェック ボックスをオフにします。

     - ボックス内をクリックし、国または地域の*名前*の入力を始めます。 フィルター処理の対象となる、サポートされている国のリストが、対応する ISO 3166-1 の 2 文字の国コードと共に表示されます。 探している国や地域が見つかったら、それを選択します。 必要な回数だけこの手順を繰り返します。

       選択した国のリストがポップアップに表示されます。 国または地域を削除するには、 ![[削除] ボタンをクリックします](../../media/scc-remove-icon.png)。

     完了したら、**[保存]** をクリックします。

8. オプションの **[迷惑メールのプロパティ]** セクションには、既定では無効になっている高度なスパム フィルター (ASF) 設定が含まれます。 ASF の設定は廃止の処理中です。この機能はフィルター処理スタックの別の部分に組み込まれます。 これらの ASF 設定はすべて、スパム対策ポリシーでオフにしておくことをお勧めします。

   これらの設定の詳細については、「[EOP での高度なスパム フィルターの設定](advanced-spam-filtering-asf-options.md)」を参照してください。

9. (必須) **[適用先]** セクションを展開して、ポリシーの適用先にする内部受信者を特定します。

    各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

    使用可能なすべての条件を表示するには、**[条件の追加]** を 3 回クリックするのが最も簡単です。 構成しない条件を削除するには、![[削除] ボタン](../../media/scc-remove-icon.png)をクリックします。

    - **[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。 **[タグの追加]** ボックスをクリックして、ドメインを表示および選択します。 複数のドメインが利用可能な場合は、**[タグの追加]** ボックスをもう一度クリックして、追加のドメインを選択します。

    - **受信者が次の場合**: 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。 **[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。 **[タグの追加]** ボックスをもう一度クリックして、追加の受信者を選択します。

    - **受信者が次のメンバーの場合**: 組織内の 1 つ以上のグループを指定します。 **[タグの追加]** をクリックして、リストをフィルター処理するための入力を始めます。 **[タグの追加]** ボックスをもう一度クリックして、追加の受信者を選択します。

    - **次の場合を除く**: ルールの例外を追加するには、**[条件の追加]** を 3 回クリックして、使用可能なすべての例外を表示します。 設定と動作は、条件とまったく同じです。

10. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>セキュリティ/コンプライアンス センターを使用してスパム対策ポリシーを表示する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックして、迷惑メール対策ポリシーを展開します。

   - 既定のポリシーには **[既定のスパム フィルター ポリシー]** という名前が付いています。

   - ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[Custom anti-spam policy]** (カスタム迷惑メール対策ポリシー) になっています。

3. 重要なポリシー設定は、ポリシー詳細を拡張すると表示されます。 詳細を表示するには、**[ポリシーの編集]** をクリックします。

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを変更する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックして、迷惑メール対策ポリシーを展開します。

   - 既定のポリシーには **[既定のスパム フィルター ポリシー]** という名前が付いています。

   - ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[Custom anti-spam policy]** (カスタム迷惑メール対策ポリシー) になっています。

3. **[ポリシーの編集]** をクリックします。

カスタム迷惑メール対策ポリシーの場合、表示されるポップアップで使用できる設定は、「[セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを作成する](#use-the-security--compliance-center-to-create-anti-spam-policies)」セクションで説明した設定と同じです。

「**既定の迷惑メール対策ポリシー**」という名前の付いた既定の迷惑メール対策ポリシーの場合、**[適用先]** セクションは選択できず (ポリシーは全員に適用される)、ポリシーの名前を変更することもできません。

ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。

### <a name="enable-or-disable-anti-spam-policies"></a>迷惑メール対策の有効化または無効化

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[迷惑メール対策の設定]** ページで ![[展開] アイコン](../../media/scc-expand-icon.png) をクリックすると、作成したカスタム ポリシーが展開されます (**[種類]** 列の値は **[カスタム迷惑メール対策ポリシー]**)。

3. 展開して表示されたポリシー詳細で、**[On]** 列の値をメモします。

   ポリシーを無効にするには、左に切り替えます。 ![オフに切り替え](../../media/scc-toggle-off.png)

   ポリシーを有効にするには、右に切り替えます。 ![オンに切り替え](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

既定の迷惑メール対策ポリシーを無効にすることはできません。

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>カスタム迷惑メール対策ポリシーの優先度を設定する

既定では、迷惑メール対策ポリシーには、ポリシーの作成順序に基づいた優先度が設定されます (新しいポリシーの優先度が古いポリシーよりも低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2 つのポリシーが同じ優先度を持つことはできません。

カスタム迷惑メール対策ポリシーは、処理される順に表示されます (最初のポリシーの値は **優先度** が 0)。 「**既定のスパム フィルター ポリシー**」という名前の付いた既定の迷惑メール対策ポリシーには値 **[Lowest]** が付いており、変更することはできません。

 **注**: セキュリティ/コンプライアンス センターでは、スパム対策ポリシーの作成後にその優先度のみを変更できます。 PowerShell では、スパム フィルター ルールの作成時に既定の優先度を上書きできます (この上書きが既存のルールの優先度に影響を与えることがあります)。

ポリシーの優先度を変更するには、リスト内で上下に移動させます (セキュリティ/コンプライアンス センター内で直接、**優先順位**番号を変更することはできません)。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[迷惑メール対策の設定]** ページで、**[種類]** 列の値が **[カスタム迷惑メール対策ポリシー]** のポリシーを検索します。 **[優先度]** 列の値に注目します。

   - 最も高い優先度を持つカスタム迷惑メール対策ポリシーの値は ![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) **0** です。

   - 最も低い優先度を持つカスタム迷惑メール対策ポリシーの値は ![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **n** です (たとえば、「![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) **3**」)。

   - 3 つ以上のカスタム迷惑メール対策ポリシーがある場合、最も高い優先度と最も低い優先度の間のポリシーの値は、![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) **n** になります (たとえば、![上矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png)![下矢印アイコン](../../media/ITPro-EAC-DownArrowIcon.png) **2**)。

3. 上 ![矢印アイコン](../../media/ITPro-EAC-UpArrowIcon.png) または ![下矢印アイコンをクリックして](../../media/ITPro-EAC-DownArrowIcon.png) ポリシー リスト内のカスタム迷惑メール対策ポリシーを上下に移動します。

### <a name="configure-end-user-spam-notifications"></a>エンドユーザーの迷惑メール通知の構成

スパム対策フィルター判定によりメッセージが検疫された場合に、受信者に送信されたメッセージに対する処理を知らせるために、エンドユーザーの迷惑メール通知を構成できます。 これらの通知の詳細については、「[EOP でのエンドユーザーの迷惑メール通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックして、迷惑メール対策ポリシーを展開します。

   - 既定のポリシーには **[既定のスパム フィルター ポリシー]** という名前が付いています。

   - ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[Custom anti-spam policy]** (カスタム迷惑メール対策ポリシー) になっています。

3. 展開して表示されたポリシー詳細で、**[エンドユーザーのスパム通知を構成する]** をクリックします。

4. **\<Policy Name\>** ダイアログが開いたら、以下の設定を行います。

   - **エンドユーザーのスパム通知を有効にする**: 通知を有効にするには、このチェックボックスを選択します。 通知を無効にするには、チェックボックスをオフにします。

   - **エンドユーザーの迷惑メール通知の送信間隔 (日)**: 通知が送信される頻度を選択します。 既定値は 3 日です。 1 日から 15 日まで入力できます。

     エンドユーザーのスパム通知は、24時間以内に 3 サイクルあります。これは、次の時間に始まります: 01:00 UTC、08:00 UTC、および 16:00 UTC。

     > [!NOTE]
     > 前回のサイクルで通知を受信できなかった場合は、後続のサイクルが通知をプッシュします。 これにより、同じ日に複数の通知が表示される場合があります。

   - **通知言語**: ドロップダウンをクリックして、リストから使用可能な言語を選びます。 既定値は、英語で、**Default**です。

   完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを削除する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。

2. **[迷惑メール対策の設定]** ページで、![[展開] アイコン](../../media/scc-expand-icon.png)をクリックし、削除するカスタム ポリシーを展開します (**[種類]** 列の値は **[カスタム迷惑メール対策ポリシー]**)。

3. 展開されたポリシー詳細で、**[ポリシーの削除]** をクリックします。

4. 警告ダイアログが表示されたら、**[はい]** をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Exchange Online PowerShell または スタンドアロン EOP PowerShell を使用して迷惑メール対策ポリシーを構成する

次の迷惑メール対策ポリシー設定は、PowerShell でのみ使用できます。

- _MarkAsSpamBulkMail_ パラメーター (既定は `On`)。 この設定の影響については、このトピックで前述した「[セキュリティ/コンプライアンス センターを使用して迷惑メール対策ポリシーを作成する](#use-the-security--compliance-center-to-create-anti-spam-policies)」で説明されています。

- 次の設定は、エンドユーザーの迷惑メール検疫通知の設定です。

  - _DownloadLink_ パラメーター。これにより、Outlook の迷惑メール報告ツールへのリンクを表示または非表示にできます。

  - _EndUserSpamNotificationCustomSubject_ パラメーター。これにより、通知の件名行をカスタマイズできます。

### <a name="use-powershell-to-create-anti-spam-policies"></a>PowerShell を使用して迷惑メール対策ポリシーを作成する

PowerShell では、2 段階の手順で迷惑メール対策ポリシーを作成します。

1. スパム フィルター ポリシーを作成する。

2. スパム フィルター ルールの適用先とするスパム フィルター ポリシーを指定するルールを作成する。

 **注**:

- 新しいスパム フィルター ルールを作成して、既存の関連付けされていないスパム フィルター ポリシーをそれに割り当てることができます。 1 つのスパム フィルター ルールを複数のスパム フィルター ポリシーに関連付けることはできません。

- ポリシーを作成してからでなければセキュリティ/コンプライアンス センターで使用できない次の設定を、PowerShell で新しいスパム フィルター ポリシーに構成できます。

  - 新しいポリシーを無効化された状態で作成する (**New-HostedContentFilterRule** コマンドレットで _Enabled_`$false` を指定)。

  - 作成時にポリシーの優先度を設定する (**New-HostedContentFilterRule** コマンドレットで _Priority_ _\<Number\>_ を指定)。

- ポリシーをスパム フィルター ルールに割り当てるまでは、PowerShell で作成した新しいスパム フィルター ポリシーをセキュリティ/コンプライアンス センターに表示することはできません。

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>手順 1: PowerShell を使用してスパム フィルター ポリシーを構成する

スパム フィルター ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次のような設定で Contoso Executives という名前のスパム フィルター ポリシーを作成します。

- スパム対策フィルター判定が「スパム」または「高確度スパム」の場合は、メッセージを検疫します。

- BCL 6 で、「バルク メール」スパム対策フィルター判定のアクションがトリガーされます。

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** と **Set-HostedContentFilterPolicy** には古い _ZapEnabled_ パラメーターと、新しい _PhishZapEnabled_ および _SpamZapEnabled_ パラメーターが含まれています。 _ZapEnabled_ パラメーターは 2020 年 2 月に廃止されました。 _PhishZapEnabled_ および _SpamZapEnabled_ パラメーターでは、値を _ZapEnabled_ パラメーターから継承して使っていました。 ただし、コマンドで _PhishZapEnabled_ や _SpamZapEnabled_ パラメーターを使用する場合や、セキュリティ/コンプライアンス センターで **[Spam ZAP]** (迷惑メールに対する ZAP) 設定や **[フィッシング詐欺に対する ZAP]** 設定を使用する場合、_ZapEnabled_ パラメーターの値は無視されます。 つまり、_ZapEnabled_ パラメーターは使用せず、代わりに _PhishZapEnabled_ および _SpamZapEnabled_ パラメーターを使用します。

構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>手順 2: PowerShell を使用してスパム フィルター ルールを作成する

スパム フィルター ルールを作成するには、次の構文を使用します。

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次に示す設定で Contoso Executives という新しいスパム フィルター ルールを作成します。

- Contoso Executives という名前のスパム フィルター ポリシーがルールに関連付けられています。

- ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

構文とパラメーターの詳細については、「[New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-view-spam-filter-policies"></a>PowerShell を使用してスパム フィルター ポリシーを表示する

すべてのスパム フィルター ポリシーの要約リストを返すには、次のコマンドを実行します。

```PowerShell
Get-HostedContentFilterPolicy
```

特定のスパム フィルター ポリシーに関する詳細情報を返すには、次の構文を使用します。

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

この例では、Executives というスパム フィルター ポリシーのすべてのプロパティの値を戻します。

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。

### <a name="use-powershell-to-view-spam-filter-rules"></a>PowerShell を使用してスパム フィルター ルールを表示する

既存のスパム フィルター ルールを表示するには、次の構文を使用します。

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

すべてのスパム フィルター ルールの要約リストを返すには、次のコマンドを実行します。

```PowerShell
Get-HostedContentFilterRule
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

特定のスパム フィルター ルールの詳細情報を返すには、次の構文を使用します。

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

この例では、Contoso Executives というスパム フィルター ルールのすべてのプロパティの値を返します。

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については、「[Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-modify-spam-filter-policies"></a>PowerShell を使用してスパム フィルター ポリシーを変更する

以下の項目以外には、このトピックで前述の「[手順 1: PowerShell を使用してスパム フィルター ポリシーを作成する](#step-1-use-powershell-to-create-a-spam-filter-policy)」で説明されたようにポリシーを作成したときと同じ設定を、PowerShell を使ってスパム フィルター ポリシーを変更するときに使用できます。

- 特定のポリシーを既定のポリシー (全員に適用され、常に **Lowest** 優先度を持ち、削除することはできない) に切り替える _MakeDefault_ スイッチは、PowerShell でスパム フィルター ポリシーを変更するときにのみ使用できます。

- スパム フィルター ポリシーの名前を変更することはできません (**Set-HostedContentFilterPolicy** コマンドレットには _Name_ パラメーターがありません)。 セキュリティ/コンプライアンス センターでスパム対策ポリシーの名前を変更する場合は、スパム フィルター _ルール_の名前を変更するだけになります。

スパム フィルター ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。

### <a name="use-powershell-to-modify-spam-filter-rules"></a>PowerShell を使用してスパム フィルター ルールを変更する

PowerShell でスパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールの作成を可能にする _Enabled_ パラメーターです。 既存のスパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。

それ以外は、PowerShell でスパム フィルター ルールを変更する際に利用可能な追加の設定はありません。 このトピックで前述の「[手順 2: PowerShell を使用してスパム フィルター ルールを作成する](#step-2-use-powershell-to-create-a-spam-filter-rule)」セクションでルールを作成したときと同じ設定を使用できます。

スパム フィルター ルールを変更するには、次の構文を使用します。

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

この例では、セキュリティ/コンプライアンス センターで問題を発生させる可能性がある `{Fabrikam Spam Filter}` という名前の既存のスパム フィルター ルールの名前を変更します。

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>PowerShell を使ってスパム フィルター ルールを有効または無効にする

PowerShell でスパム フィルター ルールを有効または無効にすると、すべての迷惑メール対策ポリシー (スパム フィルター ルールおよび割り当てられているスパム フィルター ポリシー) が有効または無効になります。 既定の迷惑メール対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。

PowerShell でスパム フィルター ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

この例では、Marketing Department というスパム フィルター ルールを無効化します。

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「[Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule)」と「[Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>PowerShell を使用してスパム フィルター ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell でスパム フィルター ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**注**:

- 新しく作成したルールの優先度を設定するには、_New-HostedContentFilterRule_ コマンドレットの **Priority** パラメーターを使用します。

- 既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールがありません。また、常に、**Lowest** の優先度が設定されており、変更はできません。

### <a name="use-powershell-to-remove-spam-filter-policies"></a>PowerShell を使用してスパム フィルター ポリシーを削除する

PowerShell を使用してスパム フィルター ポリシーを削除しても、それに対応するスパム フィルター ルールは削除されません。

PowerShell でスパム フィルター ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department というスパム フィルター ポリシーを削除します。

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「[Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy)」を参照してください。

### <a name="use-powershell-to-remove-spam-filter-rules"></a>PowerShell を使用してスパム フィルター ルールを削除する

PowerShell を使用してスパム フィルター ルールを削除しても、それに対応するスパム フィルター ポリシーは削除されません。

PowerShell でスパム フィルター ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

この例では、Marketing Department というスパム フィルター ルールを削除します。

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「[Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>GTUBE メッセージを送信して迷惑メール対策ポリシーの設定をテストする

> [!NOTE]
> これらの手順は、GTUBE メッセージを送信している電子メール組織が、送信スパムをスキャンしない場合にのみ機能します。 送信スパムをスキャンしている場合には、テスト メッセージは送信されません。

Generic Test for Unsolicited Bulk Email (GTUBE) は、テスト メッセージに組み込んで組織のスパム対策設定を検証するための文字列です。 GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。

次の GTUBE テキストを、スペースや改行なしで 1 行で電子メール メッセージに入れます。

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>許可リストと禁止リスト

メッセージがフィルターを通過してしまう場合や、システムが処理に追いつくために時間がかかる場合があります。 このような場合のために、スパム対策ポリシーには、現在の判定を上書きするために使用できる許可リストと禁止リストが用意されています。 このオプションは、リストが管理不能なほどにならないよう、控えめに使用する必要があります。また、フィルター処理スタックがその本来の処理を実行すべきであるので、一時的に使用することをお勧めします。

> [!TIP]
> 組織の判定が、このサービスが提供する判定と一致しない場合があります。 そのような場合、許可リストと禁止リストを永続的に保持することがあります。 ただし、ドメインをかなりの期間にわたって許可リストに追加するような場合は、送信者のドメインが認証済みであることを確認するように送信者に伝える必要があります。認証済みでない場合は、DMARC 拒否に設定する必要があります。
