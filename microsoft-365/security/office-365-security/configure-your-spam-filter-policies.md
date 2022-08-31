---
title: スパム フィルター ポリシーの構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者が、Exchange Online Protection (EOP) で迷惑メール対策ポリシーを表示、作成、変更、削除する方法を説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 6712359eeff1ee57ef75caea6e46452394062c43
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482364"
---
# <a name="configure-anti-spam-policies-in-eop"></a>EOP でのスパム対策ポリシーの構成

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online のメールボックスを使用している Microsoft 365 の組織、または Exchange Online のメールボックスを使用していないもののスタンドアロンの Exchange Online Protection (EOP) をお使いの組織の場合、受信メール メッセージは EOP によってスパムから自動的に保護されます。 EOP では、スパムに対する組織の全体的防御の一環として、スパム対策ポリシー (スパム フィルター ポリシーまたはコンテンツ フィルター ポリシーとも呼ばれます) を使用します。 詳細については、「[スパム対策保護](anti-spam-protection.md)」を参照してください。

管理者は、既定のスパム対策ポリシーの表示、編集、構成を行うことができます (削除はできません)。 より細かく設定できるように、カスタムのスパム対策保護ポリシーを作成し、組織内の指定したユーザー、グループ、またはドメインに適用することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

スパム対策ポリシーの構成は、Microsoft 365 Defender ポータルで、または PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 の組織向け Exchange Online PowerShell、Exchange Online メールボックスを持たない組織向けのスタンドアロン EOP PowerShell) で行います。

スパム対策ポリシーの基本的な要素は次のとおりです。

- **スパム フィルター ポリシー**: スパム フィルター判定のアクションと通知オプションを指定します。
- **スパム フィルター ルール**: スパム フィルター ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。

これら 2 つの要素の違いは、Microsoft 365 Defender ポータルでスパム対策ポリシーを管理する際には明白ではありませんが、以下の違いがあります。

- スパム対策ポリシーを作成する場合、実際にはスパム フィルター ルール、および関連付けられているスパム フィルター ポリシーの両方に同じ名前を使用して同時に作成しています。
- セキュリティ/コンプライアンス センターでスパム対策ポリシーを変更する場合、名前、優先順位、有効/無効の切り替え、そして受信者フィルターに関連する設定の変更は、実際にはスパム フィルター ルールを変更しています。他のすべての設定は、関連付けられているスパム フィルター ポリシーを変更します。
- スパム対策ポリシーを削除すると、スパム フィルター ルールおよび関連付けられたスパム フィルター ポリシーが削除されます。

Exchange Online PowerShell またはスタンドアロン EOP PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事で後述する「[Exchange Online PowerShell または スタンドアロン EOP PowerShell を使用して迷惑メール対策ポリシーを構成する](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies)」セクションを参照してください。

各組織には Default という名前の組み込みのスパム対策ポリシーがあり、以下の特徴があります。

- ポリシーに関連付けられているスパム フィルター ルール (受信者フィルター) がない場合でも、ポリシーは組織内の全受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

スパム フィルター処理の有効性を高めるために、特定のユーザーまたはユーザー グループに適用される、より厳密な設定を持つカスタムのスパム対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - スパム対策ポリシーを追加、変更、削除するには、「**組織管理**」または「**セキュリティ管理者**」役割グループのメンバーである必要があります。
  - スパム対策ポリシーに読み取り専用でアクセスするには、「**グローバル閲覧者**」あるいは「**セキュリティ閲覧者**」役割グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- スパム対策ポリシーに推奨される設定については、「[EOP スパム対策ポリシーの設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)」を参照してください。

- スパム フィルター処理を完全にオフにすることはできませんが、メール フロー ルール (トランスポート ルールとも呼ばれます) を使用して、受信メッセージのほとんどのスパム フィルター処理をバイパスできます (たとえば、サード パーティの保護サービスまたはデバイスを介してメールをルーティングしてMicrosoft 365に配信する場合など)。詳細については、「[メール フロー ルールを使用して、メッセージのスパム信頼度レベル (SCL) を設定する](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)」 を参照してください。
  - 高確度のフィッシング メッセージは、引き続きフィルター処理されます。EOP のその他の機能は影響を受けません (たとえば、メッセージは常にマルウェアをスキャンします)。
  - SecOps メールボックスまたはフィッシングシ ミュレーションのスパム フィルター処理をバイパスする必要がある場合は、メール フロー ルールを使用しないでください。 詳細については、「[サード パーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信するように構成する](configure-advanced-delivery.md)」を参照してください。

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-spam-policies"></a>Microsoft 365 Defender ポータルを使用して、スパム対策ポリシーを作成する

Microsoft 365 Defender ポータルでカスタムのスパム対策ポリシーを作成すると、スパム フィルター ルールと関連するスパム フィルター ポリシーが同時に作成され、両方に同じ名前が使われます。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[スパム対策ポリシー]** ページで、![[アイコンの作成]](../../media/m365-cc-sc-create-icon.png) **[ポリシーの作成]** の順にクリックして、ドロップ ダウンリストから **[Iインバウンド]** を選択します。

3. ポリシー ウィザードが開きます。**[ポリシーの名前を設定する]** ページで、以下の設定を構成します:
   - **[名前]**: わかりやすい一意のポリシー名を入力します。
   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **ユーザー、グループ、およびドメイン** ページで、ポリシーを適用する内部の受信者を特定します (受信者条件)。
   - **ユーザー**: 指定されたメールボックス、メール ユーザー、またはメール連絡先。
   - **グループ**: 
     - 指定された配布グループまたはメールが有効なセキュリティ グループのメンバー。
     - 指定した Microsoft 365 グループ。
   - **ドメイン**: 組織内で指定された [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)のすべての受信者。

   適正なボックスをクリックし、値の入力を開始し、結果で希望する値を選択します。 必要な回数だけこの処理を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

   ユーザーやグループには、ほとんどの識別子 (名前、表示名、エイリアス、メールアドレス、アカウント名など) を使用できますが、対応する表示名が結果に表示されます。ユーザーの場合、アスタリスク (\*) を単独で入力すると、使用可能なすべての値が表示されます。

   同じ条件の複数の値は、OR ロジックを使用します (たとえば _\<recipient1\>_ または _\<recipient2\>_)。異なる条件では AND ロジックを使用します (たとえば _\<recipient1\>_ および _\<member of group 1\>_)。

   - **これらのユーザー、グループ、およびドメインを除外する**: ポリシーが適用される内部の受信者に関する例外 (受信者の例外) を追加するには、このオプションを選択して例外を構成します。設定と動作は、条件とまったく同じです。

   > [!IMPORTANT]
   > 複数の異なる条件または例外は可算的ではありません。包括的です。 ポリシーは、指定された _すべての_ 受信者フィルターに一致する受信者 _にのみ_ 適用されます。 たとえば、次の値を使用してポリシーで受信者フィルター条件を構成します:
   >
   > - 受信者は次のとおりです: romain@contoso.com
   > - 受信者が次のメンバーの場合: Executive
   >
   > ポリシーは、Executive グループのメンバーである場合 _にのみ_、romain@contoso.com に適用されます。 グループのメンバーでない場合、ポリシーは適用されません。
   >
   > 同様に、同じ受信者フィルターをポリシーの例外として使用する場合、受信者が Executive グループのメンバーでもある場合 _にのみ_、ポリシーは romain@contoso.com に適用されません。 グループのメンバーでない場合でも、ポリシーは適用されます。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[一括メールのしきい値と迷惑メール プロパティ**] ページで、以下の設定を構成します。

   - **一括メールのしきい値**: 次のページで、**一括** スパム対策フィルター判定に指定されたアクションをトリガーするメッセージの Bulk Complaint Level (BCL) を指定します。 値が大きければ大きいほど、そのメッセージの信頼度は低い (迷惑メールである可能性が高い) ことを示します。 既定の値は 7 です。 詳細については、「[EOP の Bulk Complaint Level (BCL)](bulk-complaint-level-values.md)」および「[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)」を参照してください。

     既定では、スパム対策ポリシーでの PowerShell のみの設定である _MarkAsSpamBulkMail_ は、`On` です。 この設定は、**一括** フィルター処理判定の結果に大きく影響します。

     - **_MarkAsSpamBulkMail_ が [On]**: しきい値よりも高いまたは等しい BCL は、フィルター判定「**スパム**」に相当する SCL 6 に変換され、**一括** フィルター処理判定に指定されたアクションがメッセージに対して実行されます。
     - **_MarkAsSpamBulkMail_ が [Off]**: メッセージには BCL がスタンプされますが、**一括** フィルター処理判定に対して _何のアクションも実行されません_。 実際には、BCL しきい値と **一括** フィルター処理判定アクションは無関係です。

   - **スパム スコアを上げる**、**スパムとしてマーク**<sup>\*</sup>、**テスト モード**: 既定で、高度なスパム フィルター (ASF) の設定はオフになっています。

     これらの設定の詳細については、「[EOP での高度なスパム フィルターの設定](advanced-spam-filtering-asf-options.md)」を参照してください。

      <sup>\*</sup> **[特定の言語を含む]** と **[これらの国から]** の設定は、ASF に含まれません。

   - **特定の言語を含む**: ボックスをクリックして、ドロップダウン リストから **[オン]** または **[オフ]** を選択します。 オンにした場合は、ボックスが表示されます。 ボックスで、言語の名前の入力を始めます。 サポートされている言語のフィルター処理されたリストが表示されます。 探している言語が見つかったら、それを選択します。 必要な回数だけこの手順を繰り返します。 既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。 値の隣。

   - **これらの国から** _: ボックスをクリックして、ドロップダウン リストで *[オン]** または **[オフ]** を選択します。 オンにした場合は、ボックスが表示されます。 ボックスで、国の名前の入力を始めます。 サポートされている国のフィルター処理されたリストが表示されます。 探している国が見つかったら、それを選択します。 必要な回数だけこの手順を繰り返します。 既存の値を削除するには、値の横にある ![[アイコンの削除]](../../media/m365-cc-sc-remove-selection-icon.png) をクリックします。 値の隣。

   完了したら、**[次へ]** をクリックします。

6. **[アクション]** ページが表示されたら、次の設定を構成します。

   - **メッセージ アクション**: 以下のスパム対策フィルター判定に基づき、メッセージに対して行うアクションを選択または確認します。
     - **スパム**
     - **高確度迷惑メール**
     - **フィッシング**
     - **高確度のフィッシング**
     - **バルク**

     次の表で、スパム対策フィルター判定に使用可能なアクションを説明します。

     - チェック マーク ( ![チェック マーク。](../../media/checkmark.png)) は、アクションが使用可能であることを示します (すべてのアクションがすべての判定に使用できるわけではありません)。
     - チェック マークの後にアスタリスク ( <sup>\*</sup> ) がある場合、スパム対策フィルター判定の既定のアクションであることを示しています。

     |アクション|スパム|高<br>信頼度<br>スパム|フィッシング詐欺|高<br>信頼度<br>フィッシング詐欺|バルク|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**メッセージを迷惑メール フォルダーに移動する**: メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1</sup>|![チェック マーク。](../../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../../media/checkmark.png)<sup>\*</sup>|![チェック マーク。](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)<sup>\*</sup>|
     |**X-ヘッダーを追加する**: X-ヘッダーをメッセージ ヘッダーに追加し、そのメッセージをメールボックスに配信します。 <p> 後で **[この X ヘッダーのテキストを追加する]** ボックスに、X-ヘッダーのフィールド名 (値ではなく) を入力します。 <p> **スパム** および **高確度迷惑メール** 判定の場合、メッセージは [迷惑メール] フォルダーに移動されます。<sup>1、2</sup>|![チェック マーク。](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)||![チェック マーク](../../media/checkmark.png)|
     |**件名行の先頭にテキストを追加する**: メッセージの件名行の先頭にテキストを追加します。 メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。<sup>1、2</sup> <p> テキストを後で **[件名行の先頭にこのテキストを追加する]** ボックスに入力します。|![チェック マーク。](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)||![チェック マーク](../../media/checkmark.png)|
     |**[メッセージをメール アドレスにリダイレクトする]:** メッセージを本来の受信者の代わりに他の受信者に送信します。 <p> 後で、受信者を **[このメール アドレスにリダイレクトする]** ボックスに指定してください。|![チェック マーク。](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
     |**[メッセージの削除]:** 添付ファイルすべてを含め、メッセージ全体が確認なしで削除されます。|![チェック マーク。](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)||![チェック マーク](../../media/checkmark.png)|
     |**[メッセージを隔離する]:** メッセージを本来の受信者に送信せず、検疫に送信します。 <p> 後で、検疫でメッセージを保持する期間を **[検疫]** ボックスに指定します。 <p> 表示される **[ポリシーの選択]** ボックスで、スパム フィルター判定に対する検疫済みメッセージに適用される [検疫ポリシー](quarantine-policies.md)を指定します。詳細については、[[検疫ポリシー]](quarantine-policies.md)を参照してください。<sup>3</sup>|![チェック マーク。](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../../media/checkmark.png)<sup>\*</sup>|![チェック マーク](../../media/checkmark.png)|
     |**アクションなし**|||||![チェック マーク](../../media/checkmark.png)|

     > <sup>1</sup> EOP は、独自のメール フロー配信エージェントを使用して、迷惑メール ルールを使用するのではなく、メッセージを迷惑メール フォルダーにルーティングするようになりました。 **Set-MailboxJunkEmailConfiguration** コマンドレットの _Enabled_ パラメーターは、メール フローに影響を与えなくなりました。 詳細については、「[Exchange Online のメールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。
     >
     > EOP がオンプレミスの Exchange メールボックスを保護するハイブリット環境では、オンプレミスの Exchange でメール フロー ルール (トランスポート ルールとも言う) を構成する必要があります。これらのメール フロー ルールは、メールボックス内の迷惑メール ルールがメッセージを[迷惑メール] フォルダーに移動できるように、EOP スパム フィルター判定を解釈します。詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。
     >
     > <sup>2</sup> この値をメール フロー ルールの条件として、フィルターやルールに使用することができます。
     >
     > <sup>3</sup> 空白の **[ポリシーを選択]** 値は、特定の判定に対する既定の検疫ポリシーが使用されることを意味します。 後でスパム対策ポリシーを編集するか、設定を表示すると、既定の検疫ポリシー名が表示されます。 スパム フィルター判定に使用される既定の検疫ポリシーの詳細については[この表](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features)を参照してください。
     >
     > ユーザーは、高確率のフィッシングとして検疫された自身のメッセージを解放できません。 せいぜい、管理者が検疫ポリシーを設定し、ユーザーが検疫されている高確率のフィッシング メッセージの解放を要求できるようにする程度です。

   - **スパムを指定した日数隔離しておく**: スパム対策フィルター判定のアクションとして **[メッセージを検疫]** を選択した場合に、メッセージを検疫に保持する期間を指定します。 期間が終了すると、メッセージは削除され、回復できません。 有効な値は 1 日から 30 日です。

     > [!NOTE]
     > 既定値は、デフォルトのスパム対策ポリシーおよび PowerShell で作成した新しいスパム対策ポリシーでは15日です。 Microsoft 365Defender ポータルで作成する新しいスパム対策ポリシーの規定値は30日です。
     >
     > この設定では、**フィッシング対策** ポリシーによって検疫されたメッセージが保持される期間も制御します。 詳細については、[EOP と Defender for Office 365 内の検疫済みメッセージ](quarantine-email-messages.md)に関する記事をご覧ください。

   - **この X-ヘッダー テキストを追加する**: このボックスは、**[X-ヘッダーの追加]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。 指定する値は、メッセージ ヘッダーに追加されるヘッダー フィールドの *名前* です。 ヘッダー フィールドの *値* は常に `This message appears to be spam` です。

     最大の長さは 255 文字で、値にスペースやコロン (:) を含めることはできません。

     たとえば、値 `X-This-is-my-custom-header` を入力すると、メッセージに追加される X-ヘッダーは `X-This-is-my-custom-header: This message appears to be spam.` です。

     スペースまたはコロン (:) を含む値を入力した場合、入力した値は無視され、既定の X-ヘッダー (`X-This-Is-Spam: This message appears to be spam.`) がメッセージに追加されます。

   - **件名行の先頭にこのテキストを追加する**: このボックスは、[**件名行の先頭にテキストを追加する**] を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。メッセージの件名行の先頭に追加するテキストを入力します。

   - **このメール アドレスにリダイレクトする**: このボックスは、**[メール アドレスにリダイレクトする]** を、スパム対策フィルター判定のアクションとして選択した場合にのみ必要で、選択可能になります。 メッセージの配信先のメール アドレスを入力します。 複数の値をセミコロン (;) で区切って入力できます。

   - **安全性のヒントを有効にする**: 既定で [安全性のヒント] は有効になっていますが、これらはチェックボックスをオフにすることで無効にできます。

   - **[ゼロアワー自動消去 (ZAP) を有効にする]**: Exchange Online のメールボックスに既に配信されたメッセージを ZAP が検出し、アクションを実行します。 詳細については、「[ゼロアワー自動消去 - スパムまたはマルウェアからの保護](zero-hour-auto-purge.md)」を参照してください。

     既定では、ZAP はオンになっています。 ZAP をオンにすると、以下の設定が使用できます。

     - **フィッシング メッセージに対して ZAP を有効にする**: 既定では、ZAP はフィッシング検出に対して有効になっていますが、チェックボックスをオフにすることで無効にできます。
     - **スパム メッセージに対して ZAP を有効にする**: 既定では、ZAP はスパム検出に対して有効になっていますが、チェックボックスをオフにすることで無効にできます。

   > [!NOTE]
   > エンドユーザーのスパム通知は、サポートされているすべての保護機能 (スパム対策ポリシー判定だけでなく) の検疫済みメッセージに関する情報を含む、検疫ポリシーの _検疫通知_ に置き換えられました。検疫通知には、サポートされているすべての保護機能 (スパム対策ポリシーとフィッシング対策ポリシーの評定だけではありません) の検疫済みメッセージに関する情報が含まれています。詳細については、「[検疫ポリシー](quarantine-policies.md)」 を参照してください。

   完了したら、**[次へ]** をクリックします。

7. **[受信許可とブロック一覧]** ポップアップでは、スパム対策フィルター処理をスキップできるメッセージ送信者を、メール アドレスごと、またはメール ドメインごとに構成できます。

   **[許可]** セクションでは、許可された送信者と許可されたドメインを構成できます。 **[ブロック]** セクションでは、ブロックされた送信者とブロックされたドメインを追加できます。

   > [!IMPORTANT]
   >
   > 許可されたドメイン一覧にドメインを追加する前に慎重に検討してください。 詳細については、「[EOP での信頼できる差出人リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。
   >
   > [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)や一般的なドメイン (microsoft.com や office.com など) は、決して、許可するドメインのリストに追加しないでください。 これらのドメインがスパム対策フィルター処理をバイパスすることを許可されている場合、攻撃者はこれらの信頼できるドメインを偽装するメッセージを組織に簡単に送信できます。
   >
   > ドメインをブロックされたドメイン一覧に追加して手動でドメインを受信拒否にすることは危険ではありませんが、管理作業の負荷が増大する可能性があります。 詳細については、「[EOP での受信拒否リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。
   >
   > メッセージがフィルターを通過してしまう場合や、フィルター処理判定に同意できない場合や、システムが処理に追いつくために時間がかかる場合があります。 このような場合には、現在のフィルター処理判定を上書きするために、許可リストとブロック リストを利用することができます。 ただし、リストが管理不能なほどにならないよう、控えめで一時的なものにすることが必要です。また、フィルター処理スタックがその本来の処理を実行する必要があります。 許可されたドメインをかなりの期間にわたって保持するような場合は、送信者のドメインが認証済みであることを確認し、適宜、DMARC 拒否に設定するように、送信者に伝える必要があります。

   どのリストにもエントリを追加する手順は同じです。

   1. 構成する以下のリストのリンクをクリックします。
      - **許可された** \> **送信者**: **[送信者の管理]** をクリックします。
      - **許可された** \> **ドメイン**: **[ドメインの許可]** をクリックします。
      - **ブロックされた** \> **送信者**: **[送信者の管理]** をクリックします。
      - **ブロックされた** \> **ドメイン**: **[ドメインのブロック]** をクリックします。

   2. 表示されるポップアップで、次の手順を行います。
      1. ![[アイコンの作成]](../../media/m365-cc-sc-create-icon.png) をクリックして、**[送信者の追加]** または **[ドメインの追加]** をクリックします。
      2. 表示された **[送信者の追加]** または **[ドメインの追加]** ポップアップで、**[送信者]** ボックスまたは **[ドメイン]** ボックスのドメインで送信者のメールアドレスを入力します。 入力している間、ボックスの下に値が表示されます。 メールアドレスやドメインの入力が終わった場合は、ボックスの下にある値を選択します。
      3. 必要な回数だけ前の手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

      完了したら、**[送信者の追加]** または **[ドメインの追加]** をクリックします。

      メイン ポップアウトに戻ると、ページに追加した送信者やドメインが一覧表示されます。 このページでエントリを削除するには、以下の手順で行います。

      1. 1 つ以上のエントリをリストから選択します。 また、**検索** ボックスを使ってリスト内の値を検索することもできます。
      2. 1 つ以上のエントリを選択した後、削除アイコン ![[削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) 表示されます。
      3. [削除] アイコンをクリックする ![[削除] アイコン。](../../media/m365-cc-sc-delete-icon.png) 選択したエントリを削除します。

      完了したら、[**完了**] をクリックします。

      **[許可 & ブロック リスト]** ページに戻り、続行する場合は **[次へ]** をクリックします。

8. 表示された **[レビュー]** ページで、設定を確認します。 各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 または、**[戻る]** をクリックするか、ウィザードで特定のページを選択します。

   完了したら、**[作成]** をクリックします。

9. 表示された [確認]ページで、**[完了]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-spam-policies"></a>Microsoft 365 Defender ポータルを使用して、スパム対策ポリシーを表示する

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[スパム対策ポリシー]** ページで、以下のいずれかの値を探します。
   - **[種類]** 値は **カスタムの迷惑メール対策ポリシー** です。
   - **[名前]** 値は **迷惑メール受信対策ポリシー (既定)** です。

   迷惑メール対策ポリシーの一覧には、以下のプロパティが表示されます。

   - **名前**
   - **状態**
   - **優先度**
   - **種類**

3. 迷惑メール対策ポリシーの名前をクリックして選択すると、ポリシー設定がポップアウトで表示されます。

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-spam-policies"></a>Microsoft 365 Defender ポータルを使用して、スパム対策ポリシーを変更する

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[迷惑メール対策ポリシー]** ページで、リストから迷惑メール対策ポリシーの名前をクリックして選択します。
   - ユーザーが作成したカスタム ポリシーの場合、**[種類]** 列の値が **[カスタム 迷惑メール対策ポリシー]** になっています。
   - 既定のポリシーには、**迷惑メール受信対策ポリシー (既定)** と名前が付けられます。

3. 表示されるポリシーの詳細ポップアップで、各セクションで **[編集]** を選択して、そのセクション内の設定を変更することができます。 設定の詳細については、この以前の記事の「[Microsoft 365 Defender ポータルを使用してスパム対策ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)」セクションを参照してください。

   既定の迷惑メール対策ポリシーの場合、**[適用先]** セクションは選択できず (ポリシーは全員に適用される)、ポリシーの名前を変更することもできません。

ポリシーを有効または無効にするか、ポリシーの優先順位を設定するには、次のセクションをご覧ください。

### <a name="enable-or-disable-anti-spam-policies"></a>迷惑メール対策の有効化または無効化

既定の迷惑メール対策ポリシーを無効にすることはできません。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[迷惑メール対策ポリシー]** ページで、リストから **[カスタム 迷惑メール対策ポリシー]** の **[種類] 値** の名前をクリックして選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、以下のいずれかの値が表示されます。
   - **ポリシー オフ**: ポリシーをオンにするには、![[アイコンをオンにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オンにする]** の順にクリックします。
   - **ポリシー オン**: ポリシーをオフにするには、![[アイコンをオフにする]](../../media/m365-cc-sc-turn-on-off-icon.png)、**[オフにする]** の順にクリックします。

4. 確認ダイアログ ボックスが表示されたら、**[オンにする]** または **[オフにする]** をクリックします。

5. ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

ポリシーのメイン ページに戻ると、ポリシーの **[状態]** の値が **[オン]** または **[オフ]** になります。

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>カスタム迷惑メール対策ポリシーの優先度を設定する

既定では、迷惑メール対策ポリシーには、ポリシーの作成順序に基づいた優先度が指定されます (新しいポリシーの優先度が古いポリシーよりも低くなります)。優先度番号が小さいほど、ポリシーの優先度が高くなることを意味し (0 が最高)、ポリシーは優先度順に処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも前に処理されます)。2 つのポリシーに同じ優先度を設定することはできず、ポリシー処理は最初のポリシーが適用されると停止します。

ポリシーの優先度を変更するには、ポリシーのプロパティで [**優先度を上げる**] または [**優先度を下げる**] をクリックします (Microsoft 365 Defender ポータルの [**優先度**] の数値を直接変更することはできません)。ポリシーの優先度を変更することは、複数のポリシーを所有している場合にのみ意味があります。

 **注意**:

- Microsoft 365 Defender ポータルでは、迷惑メール対策ポリシーの優先度は、そのポリシーの作成後にのみ変更できます。PowerShell では、迷惑メール フィルター ルールの作成時に既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。
- 迷惑メール対策ポリシーは、表示される順に処理されます (最初のポリシーの値は **優先度** が 0)。 既定の迷惑メール対策ポリシーには値 **[Lowest]** が付いており、変更することはできません。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[迷惑メール対策ポリシー]** ページで、リストから **[カスタム 迷惑メール対策ポリシー]** の **[種類] 値** の名前をクリックして選択します。

3. 表示されるポリシーの詳細ポップアップの上部には、現在の優先度の値とカスタム ポリシーの数に基づいて、**[優先度を上げる]** または **[優先度を下げる]** が表示されます。
   - **優先度** 値が **0** の迷惑メール対策ポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。
   - **優先度** 値が最低の (例: **3**) 迷惑メール対策ポリシーでは、**[優先度を下げる]** オプションのみ利用可能です。
   - 3 つ以上の迷惑メール対策ポリシーがある場合、優先度の値が最も高いポリシーと最も低いポリシーの間では、**[優先度を上げる]** と **[優先度を下げる]** の両方のオプションが利用可能です。

   ![[優先度を上げる] アイコン](../../media/m365-cc-sc-increase-icon.png)、**[優先度を上げる]** の順にクリックするか、または ![[優先度を下げる] アイコン](../../media/m365-cc-sc-decrease-icon.png)、**[優先度を下げる]** の順にクリックして、**優先度** 値を変更します。

4. 完了したら、ポリシーの詳細ポップアップで **[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-spam-policies"></a>Microsoft 365 Defender ポータルを使用して、カスタムのスパム対策ポリシーを削除する

Microsoft 365 Defender ポータルを使用して、カスタム迷惑メール対策ポリシーを削除すると、スパム フィルター ルールと、それに対応するスパム フィルター ポリシーが両方とも削除されます。既定の迷惑メール対策ポリシーを削除することはできません。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. **[迷惑メール対策ポリシー]** ページで、リストから **[カスタム 迷惑メール対策ポリシー]** の **[種類] 値** の名前をクリックして選択します。 表示されるポリシーの詳細ポップアウトの上部で、![[その他の操作]](../../media/m365-cc-sc-more-actions-icon.png) アイコンをクリックします。 **[その他の操作]** \> ![[ポリシーの削除]](../../media/m365-cc-sc-delete-icon.png) アイコン **[ポリシーの削除]** の順にクリックします。

3. 確認ダイアログ ボックスが表示されたら、**[はい]** をクリックします。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Exchange Online PowerShell または スタンドアロン EOP PowerShell を使用して迷惑メール対策ポリシーを構成する

前述したように、迷惑メール対策ポリシーは、スパム フィルター ポリシーとスパム フィルター ルールから構成されます。

Exchange Online PowerShell またはスタンドアロンの EOP PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの違いは明白です。 スパム フィルター ポリシーは **\*-HostedContentFilterPolicy** コマンドレットを使用して管理し、スパム フィルター ルールは **\*-HostedContentFilterRule** コマンドレットを使用して管理します。

- PowerShell では、最初にスパム フィルター ポリシーを作成し、それからルールが適用されるポリシーを特定するスパム フィルター ルールを作成します。
- PowerShell では、スパム フィルター ポリシーとスパム フィルター ルールの設定は別々に変更します。
- PowerShell からスパム フィルター ポリシーを削除しても、対応しているスパム フィルター ルールは自動で削除されず、逆もまた同様です。

次の迷惑メール対策ポリシー設定は、PowerShell でのみ使用できます。

- _MarkAsSpamBulkMail_ パラメーター (既定は `On`)。この設定の影響については、この記事で前述した「[Microsoft 365 Defender ポータルを使用してスパム対策ポリシーを作成する](#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)」セクションで説明されています。
- 次の設定は、エンドユーザーの迷惑メール検疫通知の設定です。
  - _DownloadLink_ パラメーター。これにより、Outlook の迷惑メール報告ツールへのリンクを表示または非表示にできます。
  - _EndUserSpamNotificationCustomSubject_ パラメーター。これにより、通知の件名行をカスタマイズできます。

### <a name="use-powershell-to-create-anti-spam-policies"></a>PowerShell を使用して迷惑メール対策ポリシーを作成する

PowerShell では、2 段階の手順で迷惑メール対策ポリシーを作成します。

1. スパム フィルター ポリシーを作成する。
2. スパム フィルター ルールの適用先とするスパム フィルター ポリシーを指定するルールを作成する。

 **注**:

- 新しいスパム フィルター ルールを作成して、既存の関連付けされていないスパム フィルター ポリシーをそれに割り当てることができます。 1 つのスパム フィルター ルールを複数のスパム フィルター ポリシーに関連付けることはできません。
- ポリシーを作成するまで Microsoft 365 Defender ポータルで使用できない次の設定を、PowerShell で新しいスパム フィルター ポリシーに構成できます。
  - 新しいポリシーを無効化された状態で作成する (**New-HostedContentFilterRule** コマンドレットで _Enabled_`$false` を指定)。
  - 作成時にポリシーの優先度を設定する (**New-HostedContentFilterRule** コマンドレットで _Priority_ _\<Number\>_ を指定)。

- ポリシーをスパム フィルター ルールに割り当てるまでは、PowerShell で作成した新しいスパム フィルター ポリシーを Microsoft 365 Defender ポータルに表示することはできません。

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>手順 1: PowerShell を使用してスパム フィルター ポリシーを構成する

スパム フィルター ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次のような設定で Contoso Executives という名前のスパム フィルター ポリシーを作成します。

- スパム フィルター判定がスパムまたは高確度迷惑メールである場合に、メッセージを検疫し、検疫済みメッセージには既定の [検疫ポリシー](quarantine-policies.md)を使用します (_SpamQuarantineTag_ または _HighConfidenceSpamQuarantineTag_ パラメーターは使用していません)。
- BCL 7、8、または 9 で、「バルク メール」スパム対策フィルター判定のアクションがトリガーされます。

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

構文とパラメーターの詳細については、「[New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)」を参照してください。

> [!NOTE]
> スパム対策フィルター ポリシーで使用する[検疫ポリシー](quarantine-policies.md)を指定する詳細な手順については、「[PowerShell を使用して、スパム対策ポリシーで検疫ポリシーを指定する](quarantine-policies.md#anti-spam-policies-in-powershell)」を参照してください。

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

構文とパラメーターの詳細については、「[New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule)」を参照してください。

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

構文とパラメーターの詳細については、「[Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)」を参照してください。

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

構文とパラメーターの詳細については、「[Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-modify-spam-filter-policies"></a>PowerShell を使用してスパム フィルター ポリシーを変更する

以下の項目以外には、、PowerShell を使ってスパム フィルター ポリシーを変更する場合も、この記事で前述の「[手順 1: PowerShell を使用してスパム フィルター ポリシーを作成する](#step-1-use-powershell-to-create-a-spam-filter-policy)」で説明したポリシーを作成する場合と同じ設定を使用できます。

- 特定のポリシーを既定のポリシー (全員に適用され、常に **Lowest** 優先度を持ち、削除することはできない) に切り替える _MakeDefault_ スイッチは、PowerShell でスパム フィルター ポリシーを変更するときにのみ使用できます。
- スパム フィルター ポリシーの名前を変更することはできません (**Set-HostedContentFilterPolicy** コマンドレットには _Name_ パラメーターがありません)。 Microsoft 365 Defender ポータルでスパム対策ポリシーの名前を変更する場合は、スパム フィルター _ルール_ の名前を変更するだけになります。

スパム フィルター ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)」を参照してください。

> [!NOTE]
> スパム対策フィルター ポリシーで使用する[検疫ポリシー](quarantine-policies.md)を指定する詳細な手順については、「[PowerShell を使用して、スパム対策ポリシーで検疫ポリシーを指定する](quarantine-policies.md#anti-spam-policies-in-powershell)」を参照してください。

### <a name="use-powershell-to-modify-spam-filter-rules"></a>PowerShell を使用してスパム フィルター ルールを変更する

PowerShell でスパム フィルター ルールを変更するときに使用できない唯一の設定は、無効なルールの作成を可能にする _Enabled_ パラメーターです。既存のスパム フィルター ルールを有効または無効にするには、次のセクションを参照してください。

それ以外は、PowerShell でスパム フィルター ルールを変更する際に利用可能な追加の設定はありません。 この記事で前述の「[手順 2: PowerShell を使用してスパム フィルター ルールを作成する](#step-2-use-powershell-to-create-a-spam-filter-rule)」セクションでルールを作成したときと同じ設定を使用できます。

スパム フィルター ルールを変更するには、次の構文を使用します。

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

この例では、`{Fabrikam Spam Filter}` と名前の付けられた既存のスパム フィルター ルールの名前を変更しています。

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

構文とパラメーターの詳細については、「[Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>PowerShell を使ってスパム フィルター ルールを有効または無効にする

PowerShell でスパム フィルター ルールを有効または無効にすると、すべての迷惑メール対策ポリシー (スパム フィルター ルールおよび割り当てられているスパム フィルター ポリシー) が有効または無効になります。 既定のスパム対策ポリシーを有効または無効にできません (すべての受信者に常に適用されます)。

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

構文とパラメーターの詳細については、「[Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule)」と「[Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>PowerShell を使用してスパム フィルター ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。設定できる最低値はルールの数に依存します。たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。たとえば、カスタム ルールが五つある場合 (優先度 0 から 4) に、一つのルールの優先度を 2 に変更した場合、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

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

構文とパラメーターの詳細については、「[Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy)」を参照してください。

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

構文とパラメーターの詳細については、「[Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>GTUBE メッセージを送信して迷惑メール対策ポリシーの設定をテストする

> [!NOTE]
> これらの手順は、GTUBE メッセージを送信している電子メール組織が、送信スパムをスキャンしない場合にのみ機能します。送信スパムをスキャンしている場合には、テスト メッセージを送信できません。

Generic Test for Unsolicited Bulk Email (GTUBE) は、テスト メッセージに組み込んで組織のスパム対策設定を検証するための文字列です。 GTUBE メッセージは、マルウェア設定をテストするための European Institute for Computer Antivirus Research (EICAR) テキスト ファイルと似ています。

次の GTUBE テキストを、スペースや改行なしで 1 行で電子メール メッセージに入れます。

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
