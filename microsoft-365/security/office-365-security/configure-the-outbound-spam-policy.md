---
title: 送信スパム フィルターの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で送信スパム ポリシーを表示、作成、変更、削除する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 551c3356adb0e5c3ded15d5bf942f0ac0bbd515d
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67087662"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP の送信スパム フィルターを構成する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online またはスタンドアロン Exchange Online Protection (EOP) のメールボックスを持つ Microsoft 365 組織では、Exchange Online メールボックスがない場合、EOP 経由で送信される送信電子メール メッセージは、スパムや通常とは異なる送信アクティビティが自動的にチェックされます。

組織内のユーザーからの送信スパムは、通常、侵害されたアカウントを示します。 不審な送信メッセージは (スパム信頼レベルまたは SCL に関係なく) スパムとしてマークされ、 [高リスク配信プール](high-risk-delivery-pool-for-outbound-messages.md) を介してルーティングされ、サービスの評判を保護するのに役立ちます (つまり、Microsoft 365 ソース電子メール サーバーを IP ブロック リストから外します)。 管理者には、疑わしい送信電子メール アクティビティが自動的に通知され、 [アラート ポリシー](../../compliance/alert-policies.md)を介してブロックされたユーザーが表示されます。

EOP では、組織のスパムに対する全体的な防御の一環として、送信スパム ポリシーが使用されます。 詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。

管理者は、既定の送信スパム ポリシーを表示、編集、構成 (ただし削除) することはできません。 粒度を高めるために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタム送信スパム ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

送信スパム ポリシーは、Microsoft 365 Microsoft 365 Defender ポータルまたは PowerShell (Exchange Onlineにメールボックスを含む Microsoft 365 組織の PowerShell Exchange Online、Exchange Onlineのない組織向けのスタンドアロン EOP PowerShell で構成できます。メールボックス)。

EOP の送信スパム ポリシーの基本的な要素は次のとおりです。

- **送信スパム フィルター ポリシー: 送信スパム フィルター** の判定と通知オプションのアクションを指定します。
- **送信スパム フィルター規則: 送信スパム フィルター** ポリシーの優先度と送信者フィルター (ポリシーが適用されるユーザー) を指定します。

Microsoft 365 Defender ポータルで送信スパム ポリシーを管理する場合、これら 2 つの要素の違いは明らかではありません。

- ポリシーを作成すると、実際には、両方に同じ名前を使用して、送信スパム フィルター 規則と関連する送信スパム フィルター ポリシーを同時に作成します。
- ポリシーを変更すると、名前、優先度、有効または無効、および送信者フィルターに関連する設定によって送信スパム フィルター規則が変更されます。 その他のすべての設定では、関連付けられている送信スパム フィルター ポリシーが変更されます。
- ポリシーを削除すると、送信スパム フィルター規則と関連する送信スパム フィルター ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事で後述する[「PowerShell またはスタンドアロン EOP PowerShell Exchange Online使用して送信スパム ポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)」セクションを参照してください。

すべての組織には、次のプロパティを持つ Default という名前の組み込みの送信スパム ポリシーがあります。

- ポリシーに関連付けられている送信スパム フィルター 規則 (送信者フィルター) がない場合でも、ポリシーは組織内のすべての送信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

送信スパム フィルター処理の有効性を高めるために、特定のユーザーまたはユーザーのグループに適用されるより厳しい設定でカスタム送信スパム ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 送信スパム ポリシーを追加、変更、削除するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 送信スパム ポリシーへの読み取り専用アクセスの場合は、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 送信スパム ポリシーの推奨設定については、「 [EOP 送信スパム フィルター ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)」を参照してください。

- **送信制限を超えたEmail** という名前の既定の [アラート ポリシー](../../compliance/alert-policies.md)、**検出された不審な電子メール送信パターン**、および **ユーザーが**、送信スパムによる異常な送信電子メール アクティビティとブロックされたユーザーに関する電子メール通知を **TenantAdmins** (**グローバル管理者**) グループのメンバーに既に送信することを制限しました。 詳細については、「 [制限付きユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>Microsoft 365 Defender ポータルを使用して送信スパム ポリシーを作成する

Microsoft 365 Defender ポータルでカスタム送信スパム ポリシーを作成すると、スパム フィルター ルールと関連するスパム フィルター ポリシーが同時に作成され、両方に同じ名前が使用されます。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策の設定]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [ **スパム対策ポリシー** ] ページで、[作成] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ポリシーを作成** し、ドロップダウン リストから **[送信** ] を選択します。

3. ポリシー ウィザードが開きます。**[ポリシーの名前を設定する]** ページで、以下の設定を構成します:
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[ユーザー、グループ、ドメイン** ] ページで、ポリシーが適用される内部送信者 (受信者の条件) を特定します。
   - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 
     - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
     - 指定した Microsoft 365 グループ。
   - **ドメイン**: 組織内の指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 内のすべての送信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件の複数の値は、OR ロジックを使用します (たとえば _\<sender1\>_ または _\<sender2\>_)。異なる条件では AND ロジックを使用します (たとえば _\<sender1\>_ および _\<member of group 1\>_)。

   - **これらのユーザー、グループ、ドメインを除外する**: ポリシーが適用される内部送信者の例外 (受信者の例外) を追加するには、このオプションを選択し、例外を構成します。 設定と動作は、条件とまったく同じです。

   > [!IMPORTANT]
   > 複数の異なる種類の条件や例外は加算されません。包括的です。 ポリシーは、指定された _すべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
   >
   > - 受信者は次のとおりです: romain@contoso.com
   > - 受信者が次のメンバーの場合: Executive
   >
   > ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
   >
   > 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

   完了したら、**[次へ]** をクリックします。

5. 開いた [ **保護の設定]** ページで、次の設定を構成します。
   - **メッセージの制限**: このセクションの設定では、Exchange Online メールボックスからの送信電子メール メッセージの制限 **を** 構成します。
     - **外部メッセージの制限を設定する**: 1 時間あたりの外部受信者の最大数。
     - **内部メッセージの制限を設定** します。1 時間あたりの内部受信者の最大数。
     - **1 日のメッセージ制限を設定** する: 1 日あたりの受信者の最大数。

     有効な値は 0 ~ 10000 です。 既定値は 0 です。つまり、サービスの既定値が使用されます。 詳細については、「 [送信制限」を](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)参照してください。

    ボックスに値を入力するか、ボックスの増減矢印を使用します。

   - **メッセージの制限に達したユーザーに対する制限**: [ **保護の設定** ] セクションのいずれかの制限を超えた場合は、ドロップダウン リストからアクションを選択します。

     すべてのアクションについて、ユーザーで指定された送信者は **、電子メール アラート ポリシーの送信を制限** されています (このページの後半で **送信スパムの設定が原因で送信者がブロックされている場合は、これらのユーザーとグループに** 冗長通知を行うようになりました) は、電子メール通知を受け取ります。

     - **ユーザーのメール送信を次の日まで制限** します。これは既定値です。 Email通知が送信され、ユーザーは UTC 時刻に基づいて翌日までメッセージを送信できなくなります。 管理者がこのブロックをオーバーライドする方法はありません。
       - **ユーザーが電子メールの送信を制限** されたという名前のアラート ポリシーは、管理者に通知します (電子メールとインシデント **&アラート** \> **の表示** ページ)。
       - ポリシーで **送信スパムの送信が原因で送信者がブロックされている場合は、[特定のユーザーに通知** ] で指定されたすべての受信者にも通知されます。
       - ユーザーは、UTC 時刻に基づいて、翌日までそれ以上メッセージを送信できません。 管理者がこのブロックをオーバーライドする方法はありません。
     - **ユーザーのメール送信を制限する**:Email通知が送信され、ユーザーがMicrosoft 365 Defender ポータルで **制限付きユーザー**<https://security.microsoft.com/restrictedusers>に追加され、管理者によって **制限付きユーザー** から削除されるまで、ユーザーはメールを送信できません。管理者がリストからユーザーを削除した後、その日のユーザーは再び制限されません。 手順については、「 [スパム メールの送信後に制限付きユーザー ポータルからユーザーを削除する」を](removing-user-from-restricted-users-portal-after-spam.md)参照してください。
     - **アクションなし、アラートのみ**: Email通知が送信されます。

   - **転送ルール**: このセクションの設定を使用して、メールボックスを外部の送信者に **Exchange Online** して自動メール転送を制御します。 詳細については、「 [Microsoft 365 での自動外部メール転送の制御」を](external-email-forwarding.md)参照してください。

     > [!NOTE]
     > 自動転送が無効になっている場合、外部の送信者が転送先のメールボックスに電子メールを送信した場合、受信者は配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) を受け取ります。 メッセージが内部送信者によって送信 **され、** 転送方法が [メールボックス転送](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) ( _SMTP 転送_ とも呼ばれます) である場合、内部送信者は NDR を取得します。 受信トレイルールが原因で転送が発生した場合、内部送信者は NDR を取得しません。

     [ **自動転送ルール** ] ドロップダウン リストから、次のいずれかのアクションを選択します。

     - **自動 - システム制御**: 送信スパム フィルターを使用して、自動外部メール転送を制御できます。 これは既定の値です。
     - **オン**: ポリシーでは、自動外部メール転送は無効になりません。
     - **オフ**: すべての自動外部メール転送は、ポリシーによって無効になります。

   - **通知**: セクションの設定を使用して、不審な送信電子メール メッセージのコピーと通知を受信する必要がある追加の受信者を構成します。

     - **これらの制限を超える不審な送信のコピーをこれらのユーザーとグループに送信** します。この設定により、指定した受信者が不審な送信メッセージの Bcc フィールドに追加されます。

       > [!NOTE]
       > この設定は、既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。

       この設定を有効にするには、チェック ボックスをオンにします。 表示されたボックスで、ボックス内をクリックし、有効なメール アドレスを入力し、Enter キーを押すか、ボックスの下に表示される完全な値を選択します。

       必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   - **送信スパムの送信が原因で送信者がブロックされている場合は、これらのユーザーとグループに通知する**

     > [!IMPORTANT]
     >
     > - この設定は、送信スパム ポリシーから非推奨とされています。
     >
     > - [**受信者の制限]** セクションの制限を超えたためにユーザーがブロックされている場合、**ユーザーが電子メールの送信を制限** されたという既定の [アラート ポリシー](../../compliance/alert-policies.md)は **、既に TenantAdmins** (**グローバル管理者**) グループのメンバーに電子メール通知を送信します。 **送信スパム ポリシーのこの設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強くお勧めします**。 手順については、「 [制限付きユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

   完了したら、**[次へ]** をクリックします。

6. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[作成]** をクリックします。

7. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>Microsoft 365 Defender ポータルを使用して送信スパム ポリシーを表示する

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策の設定]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[スパム対策ポリシー]** ページで、以下のいずれかの値を探します。
   - **Type 値** は **カスタム送信スパム ポリシー** です
   - **名前** の値は **スパム対策送信ポリシーです (既定値)**

   迷惑メール対策ポリシーの一覧には、以下のプロパティが表示されます。

   - **名前**
   - **状態**
   - **優先度**
   - **種類**

3. 名前をクリックして送信スパム ポリシーを選択すると、ポリシー設定がポップアップに表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>Microsoft 365 Defender ポータルを使用して送信スパム ポリシーを変更する

1. Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。

2. [ **スパム対策ポリシー** ] ページで、名前をクリックして、一覧から送信スパム ポリシーを選択します。
   - **[種類]** 列の値が [**カスタム送信スパム ポリシー**] である場所に作成したカスタム ポリシー。
   - **スパム対策送信ポリシー (既定値) という名前の既定のポリシー**。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の「[Microsoft 365 Defender ポータルを使用して送信スパム ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies)」セクションを参照してください。

   既定の送信スパム ポリシーの場合、[ **適用対象** ] セクションは使用できず (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。

ポリシーを有効または無効にしたり、ポリシーの優先順位を設定したり、エンド ユーザー通知を構成したりするには、次のセクションを参照してください。

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>カスタム送信スパム ポリシーを有効または無効にする

既定の送信スパム ポリシーを無効にすることはできません。

1. Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。

2. [**スパム対策ポリシー**] ページで、名前をクリックして、一覧から [**カスタム送信スパム ポリシー** の **種類] の値** を持つポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>カスタム送信スパム ポリシーの優先度を設定する

既定では、送信スパム ポリシーには、作成された順序に基づく優先順位が与えられます (新しいポリシーは、以前のポリシーよりも優先順位が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (Microsoft 365 Defender ポータルの [**優先度**] の数値を直接変更することはできません)。ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

 **注意**:

- Microsoft 365 Defender ポータルでは、送信スパム ポリシーの優先度は、作成後にのみ変更できます。 PowerShell では、スパム フィルター ルールの作成時に既定の優先度を上書きできます (この上書きが既存のルールの優先度に影響を与えることがあります)。
- 送信スパム ポリシーは、表示された順序で処理されます (最初のポリシーの **優先度** の値は 0 です)。 既定の送信スパム ポリシーの優先度値は **[最低]** で、変更することはできません。

1. Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。

2. [**スパム対策ポリシー**] ページで、名前をクリックして、一覧から [**カスタム送信スパム ポリシー** の **種類] の値** を持つポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - **優先度** 値 **0** の送信スパム ポリシーには、[**優先度の低下**] オプションのみが使用できます。
   - **優先度** の値が最も低い送信スパム ポリシー (**3** など) には、[優先度の **引き上げ**] オプションのみが使用できます。
   - 送信スパム ポリシーが 3 つ以上ある場合、優先度の最大値と最小値の間のポリシーには、[ **優先度の増加** ] オプションと [優先度の **低下** ] オプションの両方が使用できます。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>Microsoft 365 Defender ポータルを使用してカスタム送信スパム ポリシーを削除する

Microsoft 365 Defender ポータルを使用してカスタム送信スパム ポリシーを削除すると、スパム フィルタールールと対応するスパム フィルター ポリシーは両方とも削除されます。 既定の送信スパム ポリシーを削除することはできません。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策の設定]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [**スパム対策ポリシー**] ページで、名前をクリックして、一覧から [**カスタム送信スパム ポリシー** の **種類] の値** を持つポリシーを選択します。 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作]](../../media/m365-cc-sc-more-actions-icon.png) アイコンをクリックします。 **[その他の操作]** \> ![[ポリシーの削除]](../../media/m365-cc-sc-delete-icon.png) アイコン **[ポリシーの削除]** の順にクリックします。

3. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する

前述のように、送信スパム ポリシーは、送信スパム フィルター ポリシーと送信スパム フィルター規則で構成されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いは明らかです。 -**HostedOutboundSpamFilterPolicy コマンドレットを\*** 使用して送信スパム フィルター ポリシーを管理し、**-HostedOutboundSpamFilterRule コマンドレットを使用\*** して送信スパム フィルター規則を管理します。

- PowerShell では、最初に送信スパム フィルター ポリシーを作成し、次にルールが適用されるポリシーを識別する送信スパム フィルター 規則を作成します。
- PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター規則の設定を個別に変更します。
- PowerShell から送信スパム フィルター ポリシーを削除しても、対応する送信スパム フィルター規則は自動的に削除されません。また、その逆も同様です。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell を使用して送信スパム ポリシーを作成する

PowerShell での送信スパム ポリシーの作成は、次の 2 段階のプロセスです。

1. 送信スパム フィルター ポリシーを作成します。
2. ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター規則を作成します。

   **注**:

   - 新しい送信スパム フィルター 規則を作成し、関連付けられていない既存の送信スパム フィルター ポリシーをそれに割り当てることができます。 送信スパム フィルター規則を複数の送信スパム フィルター ポリシーに関連付けることはできません。
   - ポリシーを作成するまで、Microsoft 365 Defender ポータルでは使用できない PowerShell の新しい送信スパム フィルター ポリシーに対して、次の設定を構成できます。
     - 無効として新しいポリシーを作成します (**New-HostedOutboundSpamFilterRule** コマンドレットで _有効)。_ `$false`
     - **New-HostedOutboundSpamFilterRule** コマンドレットの作成時のポリシーの _優先度 (優先度__\<Number\>_) を設定します。
   - PowerShell で作成した新しい送信スパム フィルター ポリシーは、送信スパム フィルター規則にポリシーを割り当てるまで、Microsoft 365 Defender ポータルに表示されません。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する

送信スパム フィルター ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、Contoso Executives という名前の新しい送信スパム フィルター ポリシーを次の設定で作成します。

- 受信者レートの制限は、既定値より小さい値に制限されます。 詳細については、「 [Microsoft 365 オプション間での送信制限」を](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)参照してください。

- いずれかの制限に達すると、ユーザーはメッセージを送信できなくなります。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

構文とパラメーターの詳細については、「 [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>手順 2: PowerShell を使用して送信スパム フィルタールールを作成する

送信スパム フィルター規則を作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Sender filters> [<Sender filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の設定を使用して Contoso Executives という名前の新しい送信スパム フィルター規則を作成します。

- Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられています。
- ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

構文とパラメーターの詳細については、「 [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule)」を参照してください。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを表示する

すべての送信スパム フィルター ポリシーの概要一覧を返すには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

特定の送信スパム フィルター ポリシーに関する詳細情報を返すには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

この例では、Executives という名前の送信スパム フィルター ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

構文とパラメーターの詳細については、「 [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)」を参照してください。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを表示する

既存の送信スパム フィルター 規則を表示するには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

すべての送信スパム フィルター規則の概要一覧を返すには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterRule
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

特定の送信スパム フィルター規則に関する詳細情報を返すには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

この例では、Contoso Executives という名前の送信スパム フィルター規則のすべてのプロパティ値を返します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については、「 [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)」を参照してください。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを変更する

この記事の「 [手順 1: PowerShell を使用して送信スパム](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) フィルター ポリシーを作成する」セクションで説明したように、PowerShell でマルウェア フィルター ポリシーを変更する場合と同じ設定を使用できます。

> [!NOTE]
> 送信スパム フィルター ポリシーの名前を変更することはできません ( **Set-HostedOutboundSpamFilterPolicy** コマンドレットには _Name_ パラメーターがありません)。 Microsoft 365 Defender ポータルで送信スパム ポリシーの名前を変更すると、送信スパム フィルター _ルール_ の名前のみが変更されます。

送信スパム フィルター ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については、「 [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)」を参照してください。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルタールールを変更する

PowerShell で送信スパム フィルター規則を変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合、PowerShell で送信スパム フィルター規則を変更しても、追加の設定は使用できません。 この記事の「 [手順 2: PowerShell を使用して送信スパム フィルタールールを作成する](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 」セクションで説明したように、ルールを作成する場合と同じ設定を使用できます。

送信スパム フィルター規則を変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については、「 [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター規則を有効または無効にする

PowerShell で送信スパム フィルター規則を有効または無効にすると、送信スパム ポリシー全体 (送信スパム フィルター規則と割り当てられた送信スパム フィルター ポリシー) 全体が有効または無効になります。 既定の送信スパム ポリシーを有効または無効にすることはできません (常にすべての送信者に適用されます)。

PowerShell で送信スパム フィルター規則を有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前の送信スパム フィルター規則を無効にします。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルタールールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で送信スパム フィルター規則の優先度を設定するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**注**:

- 作成時に新しいルールの優先度を設定するには、代わりに **New-HostedOutboundSpamFilterRule** コマンドレットの _Priority_ パラメーターを使用します。
- 送信の既定のスパム フィルター ポリシーには、対応するスパム フィルター規則がなく、変更不可の優先度値 **[最低**] が常に設定されます。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを削除する

PowerShell を使用して送信スパム フィルター ポリシーを削除する場合、対応する送信スパム フィルター規則は削除されません。

PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ポリシーを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)」を参照してください。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルタールールを削除する

PowerShell を使用して送信スパム フィルター規則を削除すると、対応する送信スパム フィルター ポリシーは削除されません。

PowerShell で送信スパム フィルター規則を削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

次の使用例は、Marketing Department という名前の送信スパム フィルター 規則を削除します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については、「 [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)」を参照してください。

## <a name="for-more-information"></a>詳細情報

[制限付きユーザー ポータルからブロックされたユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.yml)

[自動転送済みメッセージレポート](mfi-auto-forwarded-messages-report.md)
