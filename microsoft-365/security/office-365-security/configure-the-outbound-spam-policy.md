---
title: 送信スパム フィルターを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、電子メール (EOP) で送信スパム ポリシーを表示、作成、変更、および削除するExchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a799d0bfb8ebf6ae13fb01b9e34ef4266b0436e9
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53542623"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>EOP で送信スパム フィルターを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Exchange Online またはスタンドアロン Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない組織では、EOP を介して送信される送信電子メール メッセージが自動的にスパムや異常な送信アクティビティをチェックされます。

通常、組織内のユーザーからの送信スパムは、侵害されたアカウントを示します。 不審な送信メッセージはスパム (スパム信頼レベルまたは SCL に関係なく) としてマークされ、サービス[](high-risk-delivery-pool-for-outbound-messages.md)の評判を保護するために危険度の高い配信プールを経由してルーティングされます (つまり、Microsoft 365 送信元電子メール サーバーを IP ブロック リストからオフにします)。 管理者は、警告ポリシーを介して、不審な送信メール アクティビティとブロックされたユーザーに自動的 [に通知されます](../../compliance/alert-policies.md)。

EOP は、スパムに対する組織の全体的な防御の一環として、送信スパム ポリシーを使用します。 詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。

管理者は、既定の送信スパム ポリシーを表示、編集、および構成できます (ただし、削除はされません)。 さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタム送信スパム ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

送信スパム ポリシーは、Microsoft 365 Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で構成できます。

EOP の送信スパム ポリシーの基本的な要素は次のとおりです。

- **送信スパム フィルター ポリシー**: 送信スパム フィルターの評決と通知オプションのアクションを指定します。
- **送信スパム フィルター ルール**: 送信スパム フィルター ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、次のポータルで送信スパム ポリシーを管理するときにMicrosoft 365 Defenderではありません。

- ポリシーを作成すると、両方に同じ名前を使用して、実際に送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーを同時に作成します。
- ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、送信スパム フィルター ルールが変更されます。 その他の設定はすべて、関連付けられた送信スパム フィルター ポリシーを変更します。
- ポリシーを削除すると、送信スパム フィルター ルールと関連付けられた送信スパム フィルター ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半[Exchange Online「PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)またはスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する」を参照してください。

すべての組織には、次のプロパティを持つ Default という名前の組み込みの送信スパム ポリシーがあります。

- ポリシーは、ポリシーに関連付けられた送信スパム フィルター ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、Default という名前のポリシーより高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

送信スパム フィルターの効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳密な設定で、カスタムの送信スパム ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 送信スパム ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。
  - 送信スパム ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティ リーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 送信スパム ポリシーの推奨設定については、「EOP 送信スパム フィルター ポリシー [設定」を参照してください](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。

- [メール送信制限]という名前の既定のアラートポリシーが超過し、疑わしいメール送信パターンが検出され、ユーザーが既にメールを送信し、送信スパムによる異常な送信メール アクティビティとブロックされたユーザーに関する **TenantAdmins** **(グローバル** 管理者) グループのメンバーに電子メール通知を送信できません。 [](../../compliance/alert-policies.md) 詳細については、「制限付きユーザー [のアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 送信スパム ポリシーの通知オプションの代わりに、これらのアラート ポリシーを使用することをお勧めします。

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>送信スパム Microsoft 365 Defenderを作成するには、このポータルを使用します。

Microsoft 365 Defender ポータルでカスタム送信スパム ポリシーを作成すると、両方に同じ名前を使用して、スパム フィルター ルールと関連付けられたスパム フィルター ポリシーが同時に作成されます。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** ページ\>**[ポリシー]** セクション\> **[スパム対策]** の順に移動します。

2. [スパム対策 **ポリシー] ページで、[** ポリシーの作成] アイコンをクリックし、ドロップダウン リストから [送信 ![ ] ](../../media/m365-cc-sc-create-icon.png) を選択します。 

3. ポリシー ウィザードが開きます。 **［ポリシーの名前を設定する］ ページ** で、以下の設定を構成します。
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。 ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. 開く **[保護の設定]** ページで、次の設定を構成します。
   - **メッセージの制限**: このセクションの設定では、メールボックスからの送信電子メール メッセージのExchange Online構成します。
     - **外部メッセージの制限を設定する**: 1 時間あたりの外部受信者の最大数。
     - **内部メッセージの制限を設定する**: 1 時間あたりの内部受信者の最大数。
     - **1 日のメッセージ制限を設定** する: 1 日あたりの受信者の最大数。

     有効な値は 0 ~ 10000 です。 既定値は 0 で、サービスの既定値が使用されます。 詳細については、「送信制限 [」を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

    ボックスに値を入力するか、ボックスの矢印を使用します。

   - **メッセージの制限に達した** ユーザーに対する制限 : [保護の設定] セクションの制限を超えた場合に、ドロップダウン リストからアクションを選択します。

     すべてのアクションに対して **、User** で指定された受信者は、電子メール通知ポリシーの送信を制限します(また、冗長な [このページで送信スパムの送信のために送信者がブロックされている場合は、これらのユーザーとグループに通知する] で) 電子メール通知を受け取ります。

     - **ユーザーがメールを送信する日を次** の日まで制限します。これが既定値です。 電子メール通知が送信され、ユーザーは UTC 時間に基づいて、次の日までそれ以上メッセージを送信できません。 管理者がこのブロックを上書きする方法はありません。
       - メールの送信を **制限されたユーザー** という名前のアラート ポリシーは、管理者に通知します (電子メールを介して、[インシデント] &**アラートの** 表示] ページ)。 \> 
       - ポリシーの送信スパム **の送信設定** によって送信者がブロックされた場合は、特定のユーザーに通知するで指定された受信者も通知されます。
       - ユーザーは、UTC 時間に基づいて、次の日までメッセージを送信できません。 管理者がこのブロックを上書きする方法はありません。
     - メールの送信を制限する **:** 電子メール通知が送信され、ユーザーがMicrosoft 365 Defender ポータルの制限付きユーザーに追加され、管理者によって制限付きユーザーから削除されるまで、ユーザーは電子メールを送信 <https://security.microsoft.com/restrictedusers> できません。管理者がリストからユーザーを削除した後、その日のユーザーは再び制限されません。 手順については、「迷惑メールの送信後に制限付きユーザー ポータルからユーザーを削除 [する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md)。
     - **アクションなし、アラートのみ**: 電子メール通知が送信されます。

   - **転送ルール**: このセクションの設定を使用して、メールボックスから外部送信者へのExchange Online **メール** の自動転送を制御します。 詳細については、「Control automatic external email forwarding in Microsoft 365 」[を参照してください](external-email-forwarding.md)。

     > [!NOTE]
     > 自動転送が無効になっている場合、外部の送信者が転送を行っているメールボックスに電子メールを送信した場合、受信者は配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) を受信します。 メッセージが内部送信者によって送信され、転送方法がメールボックス転送 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_(SMTP_ 転送とも呼ばれる) の場合、内部送信者は NDR を取得します。 受信トレイ ルールが原因で転送が発生した場合、内部送信者は NDR を取得されません。

     [自動転送ルール] ドロップダウン リストから次のいずれかの **アクション** を選択します。

     - **自動 - システム制御**: 送信スパム フィルターを使用して、外部メールの自動転送を制御できます。 これが既定値です。
     - **On**: ポリシーによって外部メールの自動転送は無効にされません。
     - **オフ**: ポリシーによってすべての自動外部メール転送が無効になります。

   - **通知**: セクションの設定を使用して、不審な送信メール メッセージのコピーと通知を受け取る必要がある追加の受信者を構成します。

     - **これらのユーザーおよびグループに** 対して、これらの制限を超える疑わしい送信のコピーを送信する : この設定では、指定した受信者を不審な送信メッセージの BCC フィールドに追加します。

       > [!NOTE]
       > この設定は、既定の送信スパム ポリシーでのみ機能します。 作成したカスタム送信スパム ポリシーでは機能しません。

       この設定を有効にするには、チェック ボックスをオンにします。 表示されるボックスで、ボックス内をクリックし、有効なメール アドレスを入力し、Enter キーを押するか、ボックスの下に表示される完全な値を選択します。

       必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   - **送信スパムの送信によって送信者がブロックされた場合、これらのユーザーとグループに通知する**

     > [!IMPORTANT]
     >
     > - この設定は、送信スパム ポリシーから廃止される過程です。
     >
     > - [受信者 [](../../compliance/alert-policies.md)の制限]セクションの制限を超えてユーザーがブロックされた場合、ユーザーが電子メールの送信を制限された既定のアラート ポリシーは **、TenantAdmins** ( Global  **admins**) グループのメンバーに電子メール通知を既に送信します。 **送信スパム ポリシーでこの** 設定ではなく、アラート ポリシーを使用して管理者や他のユーザーに通知することを強く推奨します。 手順については、「制限付き [ユーザーのアラート設定を確認する」を参照してください](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

   完了したら、**[次へ]** をクリックします。

6. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[作成]** をクリックします。

7. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>送信スパム ポリシー Microsoft 365 Defenderを表示するには、このポータルを使用します。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** ページ\>**[ポリシー]** セクション\> **[スパム対策]** の順に移動します。

2. **[スパム対策ポリシー]** ページで、以下のいずれかの値を探します。
   - Type **値は** 、 **ユーザー設定の送信スパム ポリシーです。**
   - Name **値** はスパム **対策送信ポリシーです (既定)**

   迷惑メール対策ポリシーの一覧には、以下のプロパティが表示されます。

   - **名前**
   - **状態**
   - **優先度**
   - **種類**

3. 名前をクリックして送信スパム ポリシーを選択すると、ポリシー設定がフライアウトに表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>送信スパム ポリシー Microsoft 365 Defender変更する場合は、このポータルを使用します。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** ページ\>**[ポリシー]** セクション\> **[スパム対策]** の順に移動します。

2. [スパム **対策ポリシー] ページ** で、名前をクリックして一覧から送信スパム ポリシーを選択します。
   - [種類] 列の値が [カスタム送信スパム ポリシー] であるカスタム **ポリシーを作成しました**。
   - スパム対策送信ポリシー **(Default) という名前の既定のポリシー** です。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の「Microsoft 365 Defender[](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies)を使用して送信スパム ポリシーを作成する」を参照してください。

   既定の送信スパム ポリシーの場合、[適用対象] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更できません。

ポリシーを有効または無効にするには、ポリシーの優先順位を設定するか、またはエンドユーザーの検疫通知を構成します。後続の各セクションをご覧ください。

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>カスタム送信スパム ポリシーを有効または無効にする

既定の送信スパム ポリシーを無効にできない。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** ページ\>**[ポリシー]** セクション\> **[スパム対策]** の順に移動します。

2. [スパム **対策ポリシー]** ページで、名前をクリックして、リストから[カスタム送信スパム ポリシーの種類] 値を持つポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>カスタム送信スパム ポリシーの優先度を設定する

既定では、送信スパム ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、古いポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで **[優先度を上げる]** または **[優先度を下げる]** をクリックします (Microsoft 365 Defender ポータルの **[優先度]** の数値を直接変更することはできません)。 ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

 **注意**:

- このポータルMicrosoft 365 Defender、送信スパム ポリシーを作成した後にのみ、その優先度を変更できます。 PowerShell では、スパム フィルター ルールの作成時に既定の優先度を上書きできます (この上書きが既存のルールの優先度に影響を与えることがあります)。
- 送信スパム ポリシーは、表示順に処理されます (最初のポリシーの **優先度** は 0 です)。 既定の送信スパム ポリシーの優先度の値は **[最低**] で、変更は行ないます。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** ページ\>**[ポリシー]** セクション\> **[スパム対策]** の順に移動します。

2. [スパム **対策ポリシー]** ページで、名前をクリックして、リストから[カスタム送信スパム ポリシーの種類] 値を持つポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - 優先度の値が **0** の送信スパム **ポリシー** には、[優先度の下がり]**オプション** しか使用できません。
   - 優先度の値が最も低い送信スパム ポリシー (**たとえば、3)** には、[優先度の引き上げ]**オプション** しか使用できません。
   - 3 つ以上の送信スパム ポリシーがある場合、優先度の高い値と最も低い優先度の間のポリシーには、[優先度の引き上げ] オプションと [優先度の低下] の両方 **のオプションがあります**。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>カスタムの送信Microsoft 365 Defenderポリシーを削除するには、このポータルを使用します。

Microsoft 365 Defenderポータルを使用してカスタム送信スパム ポリシーを削除すると、スパム フィルター ルールと対応するスパム フィルター ポリシーの両方が削除されます。 既定の送信スパム ポリシーを削除できない。

1. Microsoft 365 Defender ポータルで、**[メールと共同作業]** \>**[ポリシーとルール]** \> **[脅威ポリシー]** ページ\>**[ポリシー]** セクション\> **[スパム対策]** の順に移動します。

2. [スパム **対策ポリシー]** ページで、名前をクリックして、リストから[カスタム送信スパム ポリシーの種類] 値を持つポリシーを選択します。 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作] アイコン](../../media/m365-cc-sc-more-actions-icon.png)、**[その他の操作]** \>、![[ポリシーの削除] アイコン](../../media/m365-cc-sc-delete-icon.png)、**[ポリシーの削除]** の順にクリックします。

3. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して送信スパム ポリシーを構成する

前述したように、送信スパム ポリシーは、送信スパム フィルター ポリシーと送信スパム フィルター ルールで構成されます。

PowerShell Exchange Onlineスタンドアロン EOP PowerShell では、送信スパム フィルター ポリシーと送信スパム フィルター ルールの違いが明らかです。 **\* -HostedOutboundSpamFilterPolicy** コマンドレットを使用して送信スパム フィルター ポリシーを管理し **\* 、-HostedOutboundSpamFilterRule** コマンドレットを使用して送信スパム フィルター ルールを管理します。

- PowerShell では、最初に送信スパム フィルター ポリシーを作成してから、ルールが適用されるポリシーを識別する送信スパム フィルター ルールを作成します。
- PowerShell では、送信スパム フィルター ポリシーの設定と送信スパム フィルター ルールを個別に変更します。
- PowerShell から送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell を使用して送信スパム ポリシーを作成する

PowerShell で送信スパム ポリシーを作成するには、次の 2 つの手順を実行します。

1. 送信スパム フィルター ポリシーを作成します。
2. ルールが適用される送信スパム フィルター ポリシーを指定する送信スパム フィルター ルールを作成します。

   **注意**: 

   - 新しい送信スパム フィルター ルールを作成し、関連付けされていない既存の送信スパム フィルター ポリシーを割り当てできます。 送信スパム フィルター ルールを複数の送信スパム フィルター ポリシーに関連付けできない。
   - ポリシーの作成後まで、Microsoft 365 Defender ポータルで使用できない PowerShell の新しい送信スパム フィルター ポリシーに対して、次の設定を構成できます。
     - 無効として新しいポリシーを作成 _します_ `$false` **(New-HostedOutboundSpamFilterRule コマンドレットで有効** )。
     -  _\<Number\>_ **New-HostedOutboundSpamFilterRule** コマンドレットの作成時のポリシーの優先度 (優先度) を設定します。
   - PowerShell で作成した新しい送信スパム フィルター ポリシーは、ポリシーを送信スパム フィルター ルールに割り当てるまで、Microsoft 365 Defender ポータルに表示されません。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>手順 1: PowerShell を使用して送信スパム フィルター ポリシーを作成する

送信スパム フィルター ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、Contoso Executives という名前の新しい送信スパム フィルター ポリシーを次の設定で作成します。

- 受信者レートの制限は、既定値の小さい値に制限されます。 詳細については[、「Sending limits across Microsoft 365」 を参照してください](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 制限の 1 つに達すると、ユーザーはメッセージを送信できません。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>手順 2: PowerShell を使用して送信スパム フィルター ルールを作成する

送信スパム フィルター ルールを作成するには、次の構文を使用します。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、Contoso Executives という名前の新しい送信スパム フィルター ルールを次の設定で作成します。

- Contoso Executives という名前の送信スパム フィルター ポリシーがルールに関連付けられている。
- ルールは Contoso Executives Group という名前のグループのメンバーに適用されます。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

構文とパラメーターの詳細については [、「New-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを表示する

すべての送信スパム フィルター ポリシーの概要リストを取得するには、次のコマンドを実行します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

特定の送信スパム フィルター ポリシーに関する詳細情報を取得するには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

この例では、Executives という名前の送信スパム フィルター ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを表示する

既存の送信スパム フィルター ルールを表示するには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

すべての送信スパム フィルター ルールの概要リストを取得するには、次のコマンドを実行します。

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

特定の送信スパム フィルター ルールに関する詳細情報を取得するには、次の構文を使用します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

この例では、Contoso Executives という名前の送信スパム フィルター ルールのすべてのプロパティ値を返します。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

構文とパラメーターの詳細については [、「Get-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを変更する

この記事の「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) を使用して送信スパム フィルター ポリシーを作成する」で説明したように、PowerShell でマルウェア フィルター ポリシーを変更する場合と同じ設定を使用できます。

> [!NOTE]
> 送信スパム フィルター ポリシーの名前を変更することはできません **(Set-HostedOutboundSpamFilterPolicy** コマンドレットには _Name_ パラメーターはありません)。 Microsoft 365 Defender ポータルで送信スパム ポリシーの名前を変更する場合は、送信スパム フィルター ルールの名前を変更 _する_ のみです。

送信スパム フィルター ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを変更する

PowerShell で送信スパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存の送信スパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、PowerShell で送信スパム フィルター ルールを変更するときに追加の設定を使用できません。 この記事の「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) を使用して送信スパム フィルター ルールを作成する」セクションで説明したように、ルールを作成する場合も同じ設定を使用できます。

送信スパム フィルター ルールを変更するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを有効または無効にする

PowerShell で送信スパム フィルター ルールを有効または無効にすると、送信スパム ポリシー全体 (送信スパム フィルター ルールと割り当てられた送信スパム フィルター ポリシー) が有効または無効となります。 既定の送信スパム ポリシーを有効または無効にできない (常にすべての受信者に適用されます)。

PowerShell で送信スパム フィルター ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

この例では、マーケティング部門という名前の送信スパム フィルター ルールを無効にします。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Enable-HostedOutboundSpamFilterRule」](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) および [「Disable-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell で送信スパム フィルター ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**注**:

- 新しいルールを作成するときに優先度を設定するには、代わりに **New-HostedOutboundSpamFilterRule** コマンドレットの Priority パラメーターを使用します。 
- 送信の既定のスパム フィルター ポリシーには、対応するスパム フィルター ルールが含めず、常に変更できない優先度の値が **最低です**。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell を使用して送信スパム フィルター ポリシーを削除する

PowerShell を使用して送信スパム フィルター ポリシーを削除すると、対応する送信スパム フィルター ルールは削除されません。

PowerShell で送信スパム フィルター ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ポリシーを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterPolicy」を参照してください](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell を使用して送信スパム フィルター ルールを削除する

PowerShell を使用して送信スパム フィルター ルールを削除すると、対応する送信スパム フィルター ポリシーは削除されません。

PowerShell で送信スパム フィルター ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前の送信スパム フィルター ルールを削除します。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-HostedOutboundSpamFilterRule」を参照してください](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>詳細情報

[制限されたユーザー ポータルからブロックされたユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.yml)

[自動転送済みメッセージレポート](mfi-auto-forwarded-messages-report.md)
