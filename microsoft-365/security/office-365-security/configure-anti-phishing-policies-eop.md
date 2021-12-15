---
title: EOP でのスパム対策ポリシーの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
description: 管理者は、Exchange Online Protection (EOP) 組織で使用できるフィッシング対策ポリシーを作成、変更、および削除する方法について説明します(Exchange Online メールボックスを使用する場合と使用しない場合)。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b80a512c4428d897b8ef16c673fc47700b017e40
ms.sourcegitcommit: b6ab10ba95e4b986065c51179ead3810cc1e2a85
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61520958"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>EOP でのスパム対策ポリシーの構成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)

Exchange Online メールボックスのない Exchange Online 組織またはスタンドアロン Exchange Online Protection (EOP) 組織の Microsoft 365 組織では、有効になっているスプーフィング対策機能の数が制限されている既定のフィッシング対策ポリシーがあります。既定で。 詳細については、「[フィッシング詐欺対策ポリシーでのなりすまし設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。

管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (ただし、削除はされません)。 さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

メールボックスがExchange Online組織は、Microsoft 365 Defender ポータルまたは PowerShell でフィッシングExchange Online構成できます。 スタンドアロン EOP 組織は、このポータルMicrosoft 365 Defenderできます。

microsoft Defender for Office 365 で使用できる、より高度なフィッシング対策ポリシーを作成および変更する方法については[、「Configure anti-フィッシング](configure-mdo-anti-phishing-policies.md)ポリシー in Microsoft Defender for Office 365」を参照してください。

フィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。
- **フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、フィッシング対策ポリシーを管理する際に、Microsoft 365 Defenderされません。

- フィッシング対策ポリシーを作成する場合は、両方に同じ名前を使用して、実際にフィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。
- フィッシング対策ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、フィッシング対策ルールが変更されます。 その他の設定はすべて、関連付けられたフィッシング対策ポリシーを変更します。
- フィッシング対策ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。

PowerShell Exchange Onlineでは、ポリシーとルールを個別に管理します。 詳細については、この記事の[後半Exchange Online「PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies)を使用してフィッシング対策ポリシーを構成する」を参照してください。

すべての組織には、次のプロパティを持つ Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。

- ポリシーは、ポリシーに関連付けられたフィッシング対策ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

フィッシング対策保護の効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定で、カスタムのフィッシング対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">https://security.microsoft.com</a> で Microsoft 365 Defender ポータルを開きます。 フィッシング対策ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

  スタンドアロン EOP PowerShell ではフィッシング対策ポリシーを管理できない。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - フィッシング対策ポリシーを追加、変更、削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - フィッシング対策ポリシーへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティ リーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [**組織の管理の表示のみ**][](/Exchange/permissions-exo/permissions-exo#role-groups)役割グループは、Exchange Online機能への読み取り専用アクセスも提供します <sup>\*</sup> 。

- フィッシング対策ポリシーの推奨設定については、「EOP フィッシング対策ポリシー設定」 [を参照してください](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)。

- 更新されたポリシーを適用するには、最大 30 分かかります。

- フィルター 処理パイプラインでフィッシング対策ポリシーが適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>フィッシング対策Microsoft 365 Defenderを作成するには、このポータルを使用します。

Microsoft 365 Defender ポータルでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。

1. [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。

2. [フィッシング **対策] ページで、[作成** ] アイコン ![ をクリックします。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. ポリシー ウィザードが開きます。 [ポリシー名 **] ページで** 、次の設定を構成します。
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 組織内で指定された 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 組織内で指定された配布グループ、メール対応セキュリティ グループ、または Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 別の条件では、AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) を使用します。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[フィッシング&の** しきい値] ページで、[スプーフィング インテリジェンスを有効にする] チェック ボックスを使用してスプーフィング インテリジェンスのオンとオフを切り替えます。 既定値はオン (選択) であり、オンのままにすることをお勧めします。 次のページで、ブロックされたスプーフィングされたメッセージに対して実行するアクションを構成します。

   スプーフィング インテリジェンスをオフにするには、チェック ボックスをオフにします。

   > [!NOTE]
   > MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング防止保護をオフにする必要があります。代わりに、コネクタの拡張フィルターを有効にします。 手順については、「拡張フィルタリング[for Connectors in Exchange Online」 を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   完了したら、**[次へ]** をクリックします。

6. **[アクション]** ページが表示されたら、次の設定を構成します。
   - **メッセージがスプーフィングとして検出された** 場合: この設定は、前のページで [スプーフィング インテリジェンスを有効にする] を選択した場合にのみ使用できます。 ブロックされたスプーフィングされた送信者からのメッセージについては、ドロップダウン リストで次のいずれかのアクションを選択します。
     - **受信者の迷惑メール フォルダーにメッセージを移動する**
     - **メッセージを検疫する**: このアクションを選択すると、[検疫ポリシーの適用] ボックスが表示され、スプーフィング インテリジェンス保護によって検疫されるメッセージに適用される検疫ポリシーを選択します。 検疫ポリシーは、検疫されたメッセージに対してユーザーが実行できる操作と、ユーザーが検疫通知を受け取るかどうかを定義します。 詳細については、「[検疫ポリシー](quarantine-policies.md)」を参照してください。

       [検疫 **ポリシーの適用]** の値が空白の場合は、既定の検疫ポリシーが使用されます (スプーフィング インテリジェンス検出の場合は DefaultFullAccessPolicy)。 後でフィッシング対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。 サポートされている保護フィルターの評決に使用される既定の検疫ポリシーの詳細については、次の表を [参照してください](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)。

   - **安全上のヒント&インジケーター**:
     - **最初の連絡先の安全性のヒント** を表示する : 詳細については [、「First contact 安全性のヒント」 を参照してください](set-up-anti-phishing-policies.md#first-contact-safety-tip)。
     - **ス** プーフィングの認証されていない送信者に対して (?) を表示する : メッセージが SPF チェックまたは DKIM チェックに合格しない場合に、メッセージが DMARC または複合認証に合格しない場合に、Outlook の [差出人] ボックスの送信者の写真に疑問符 <sup>\*</sup> (?)[](email-validation-and-authentication.md#composite-authentication)を追加します。
     - **"via"** タグを表示する: DKIM 署名または MAIL FROM アドレスのドメインと異なる場合は、from アドレスに via タグ (chris@contoso.com 経由で <sup>\*</sup> fabrikam.com) を **追加** します。

     設定を有効にする場合は、チェック ボックスをオンにします。 オフにする場合は、チェック ボックスをオフにします。

     <sup>\*</sup> この設定は、前のページで [スプーフィング インテリジェンスを有効 **にする** ] を選択した場合にのみ使用できます。 詳細については、「認証されていない送信者 [」を参照してください](set-up-anti-phishing-policies.md#unauthenticated-sender)。

   完了したら、**[次へ]** をクリックします。

7. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[送信]** をクリックします。

8. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>フィッシング対策Microsoft 365 Defenderを表示するには、このポータルを使用します。

1. [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。

2. [フィッシング **対策] ページで** 、ポリシーの一覧に次のプロパティが表示されます。

   - **名前**
   - **状態**
   - **優先度**
   - **最終更新日時**

3. 名前をクリックしてポリシーを選択すると、ポリシー設定がフライアウトに表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>フィッシング対策Microsoft 365 Defenderポータルを使用して変更する

1. [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックして一覧からポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この記事の「[](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies)フィッシング対策ポリシーを作成Microsoft 365 Defenderを使用してフィッシング対策ポリシーを作成する」を参照してください。

   既定のフィッシング対策ポリシーでは、[ユーザー、グループ、ドメイン] セクションは使用できません (ポリシーはすべてのユーザーに適用されます)、ポリシーの名前を変更することはできません。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションをご覧ください。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーを有効または無効にする

既定のフィッシング対策ポリシーを無効にできない。

1. [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーの優先度を設定する

既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (Microsoft 365 Defender ポータルの [**優先度**] の数値を直接変更することはできません)。ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

 **注意**:

- このポータルMicrosoft 365 Defender、フィッシング対策ポリシーの優先度を変更できるのは、作成後のみです。 PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。
- フィッシング対策ポリシーは、表示順に処理されます (最初のポリシーの **優先度** は 0 です)。 既定のフィッシング対策ポリシーの優先度の値は **[最低**] で、変更は行えなくないます。

1. [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - 優先度の値が **0** **のポリシー** には、[優先度を下にする]**オプションしか** 使用できません。
   - 優先度の値が最も **低い** ポリシー ( **たとえば、3)** には、[優先度の引き上げ] **オプション** しか使用できません。
   - 3 つ以上のポリシーがある場合、優先度の高い値と最も低い優先度の値の間のポリシーには、[優先度の引き上げ] オプションと [優先度の下 **げ]** の両方 **のオプションがあります** 。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>カスタムフィッシングMicrosoft 365 Defenderポリシーを削除するには、このポータルを使用します。

Microsoft 365 Defenderポータルを使用してカスタムフィッシング対策ポリシーを削除すると、フィッシング対策ルールと対応するフィッシング対策ポリシーの両方が削除されます。 既定のフィッシング対策ポリシーを削除できない。

1. [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。

2. [フィッシング **対策] ページで** 、名前をクリックしてリストからカスタム ポリシーを選択します。

3. 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作]](../../media/m365-cc-sc-more-actions-icon.png) アイコンをクリックします。 **[その他の操作]** \> ![[ポリシーの削除]](../../media/m365-cc-sc-delete-icon.png) アイコン **[ポリシーの削除]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>PowerShell Exchange Onlineを使用してフィッシング対策ポリシーを構成する

前述したように、フィッシング対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されています。

PowerShell Exchange Online、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。 -AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。 **\***

- PowerShell では、最初にフィッシング対策ポリシーを作成してから、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。
- PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。
- PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。

> [!NOTE]
> 次の PowerShell 手順は、PowerShell を使用してスタンドアロンの EOP 組織ではExchange Online Protectionできません。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。

1. フィッシング対策ポリシーを作成します。
2. ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。

 **注**:

- 新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。 フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けできない。

- ポリシーの作成後まで、Microsoft 365 Defender ポータルで使用できない PowerShell の新しいフィッシング対策ポリシーで次の設定を構成できます。

  - 無効として新しいポリシーを作成 _します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-AntiPhishRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策ルールに割り当てるまで、Microsoft 365 Defender ポータルに表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する

フィッシング対策ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>] [-SpoofQuarantineTag <QuarantineTagName>]
```

この例では、次の設定を使用して、Research Quarantine という名前のフィッシング対策ポリシーを作成します。

- 説明は、調査部門のポリシーです。
- スプーフィング検出の既定のアクションを [検疫][](quarantine-policies.md)に変更し、検疫済みメッセージに既定の検疫ポリシーを _使用_ します (スプーフィンクエリアンタグ パラメーターは使用しません)。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

構文とパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](/powershell/module/exchange/New-AntiPhishPolicy)。

> [!NOTE]
> フィッシング対策ポリシーで使用する検疫ポリシー[](quarantine-policies.md)を指定する詳細な手順については[、「Use PowerShell](quarantine-policies.md#anti-phishing-policies)を使用してフィッシング対策ポリシーで検疫ポリシーを指定する」を参照してください。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>手順 2: PowerShell を使用してフィッシング対策ルールを作成する

フィッシング対策ルールを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の条件を使用して、Research Department という名前のフィッシング対策ルールを作成します。

- ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。
- ルールは Research Department という名前のグループのメンバーに適用されます。
- Priority パラメーターを使用していないので _、既定_ の優先度が使用されます。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

構文とパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを表示する

既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

次の使用例は、指定したプロパティと共に、すべてのフィッシング対策ポリシーの概要リストを返します。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

構文とパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを表示する

既存のフィッシング対策ルールを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと共に、すべてのフィッシング対策ルールの概要リストを返します。

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

ルールを有効または無効にしてリストをフィルター処理するには、次のコマンドを実行します。

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

構文とパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを変更する

次の項目以外にも、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング対策ポリシーを作成する」で説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。

- 指定したポリシーを既定のポリシーに変換する _MakeDefault_ スイッチ (すべてのユーザーに適用され、常に優先度が最も低く、削除できません) は、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。
- フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。 Microsoft 365 Defender ポータルでフィッシング対策ポリシーの名前を変更すると、フィッシング対策ルールの名前が変更 _されます_。

フィッシング対策ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Set-AntiPhishPolicy)。

> [!NOTE]
> フィッシング対策ポリシーで使用する検疫ポリシー[](quarantine-policies.md)を指定する詳細な手順については[、「Use PowerShell を](quarantine-policies.md#anti-phishing-policies)使用してフィッシング対策ポリシーで検疫ポリシーを指定する」を参照してください。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを変更する

PowerShell でフィッシング対策ルールを変更するときに使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成するときに同じ設定を使用できます。

フィッシング対策ルールを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを有効または無効にする

PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) 全体が有効または無効となります。 既定のフィッシング対策ポリシーを有効または無効にできない (すべての受信者に常に適用されます)。

PowerShell でフィッシング対策ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前のフィッシング対策ルールを無効にします。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Enable-AntiPhishRule」](/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](/powershell/module/exchange/disable-antiphishrule)。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注**:

- 新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの Priority パラメーターを使用します。 
- 既定のフィッシング対策ポリシーには、対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値が **[最低**] です。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを削除する

PowerShell を使用してフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは削除されません。

PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを削除する

PowerShell を使用してフィッシング対策ルールを削除すると、対応するフィッシング対策ポリシーは削除されません。

PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ルールを削除します。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

構文とパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

EOP でフィッシング対策ポリシーが正常に構成されたことを確認するには、次の手順を実行します。

- [ポリシー <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] Microsoft 365 Defenderで</a>、[ポリシー]セクションの&ルール脅威ポリシー&フィッシング対策ポリシーにメールを送信する」 \>  \>  \> **に移動** します。 ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。 詳細を表示するには、名前をクリックして表示されるフライアウトの詳細を表示して、一覧からポリシーを選択します。

- PowerShell Exchange Online、ポリシーまたはルールの名前に置き換え、次のコマンドを実行 \<Name\> し、設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
