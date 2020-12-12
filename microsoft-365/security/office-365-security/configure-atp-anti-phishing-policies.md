---
title: Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Microsoft Defender for Office 365 の組織で利用可能な高度なフィッシング対策ポリシーを作成、変更、削除する方法について説明します。
ms.openlocfilehash: 295600098aee151ec088e48345bf69181ba3afb8
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658896"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[microsoft Defender for Office 365](office-365-atp.md)のフィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃や他の種類のフィッシング攻撃から組織を保護するのに役立ちます。 Exchange Online Protection (EOP) のフィッシング対策ポリシーと Microsoft Defender for Office 365 のフィッシング対策ポリシーの違いの詳細については、「フィッシング対策保護[](anti-phishing-protection.md)」を参照してください。

管理者は、既定のフィッシング詐欺対策ポリシーを表示、編集、構成 (削除しない) できます。 よりきめ細かく管理するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

フィッシング対策ポリシーは、セキュリティ/コンプライアンス センターまたは Exchange Online PowerShell &構成できます。

Exchange Online Protection 組織 (つまり、Microsoft Defender for Office 365 を使用しない組織) で使用可能なフィッシング対策ポリシーの構成の詳細については [、「EOP](configure-anti-phishing-policies-eop.md)でフィッシング対策ポリシーを構成する」を参照してください。

フィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシング対策ポリシー**: 有効または無効にするフィッシング対策と、オプションを適用するアクションを指定します。
- **フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、セキュリティ/コンプライアンス センターでフィッシング対策ポリシーを管理&明らかではありません。

- ポリシーを作成する場合、実際には、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。
- ポリシーを変更すると、名前、優先度、有効または無効、受信者フィルターに関連する設定によってフィッシング対策ルールが変更されます。 その他のすべての設定では、関連するフィッシング対策ポリシーが変更されます。
- ポリシーを削除すると、フィッシング対策ルールと関連するフィッシング対策ポリシーが削除されます。

Exchange Online PowerShell では、ポリシーとルールを個別に管理します。 詳細については、後の「Exchange Online PowerShell を使用して [Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) のフィッシング対策ポリシーを構成する」を参照してください。

Office 365 組織のすべての Microsoft Defender には、次のプロパティを持つ Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。

- ポリシーに関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

microsoft Defender for Office 365 のフィッシング対策保護の効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定を使用して、カスタムのフィッシング対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 ATP フィッシング詐欺対策ページ **に直接移動するには** 、次のコマンドを使用します <https://protection.office.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - フィッシング対策ポリシーを追加、変更、および削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - フィッシング対策ポリシーへの読み取り専用アクセスの場合、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要** があります <sup>\*</sup> 。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) **の View-Only Organization Management** 役割グループは、この機能への読み取り専用アクセスも提供します <sup>\*</sup> 。
  - <sup>\*</sup> セキュリティ センターコンプライアンス センター&読み取り専用アクセスにより、ユーザーはカスタムフィッシング対策ポリシーの設定を表示できます。 読み取り専用のユーザーは、既定のフィッシング対策ポリシーの設定を表示できない。

- microsoft Defender for Office 365 のフィッシング対策ポリシーに関する推奨設定については、Defender のフィッシング対策ポリシー (Office [365](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)の設定) を参照してください。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- フィッシング対策ポリシーがフィルター パイプラインで適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 でフィッシング対策ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。

フィッシング対策ポリシーを作成する場合、ポリシーの名前、説明、およびポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。 ポリシーを作成した後、ポリシーを変更して、既定のフィッシング対策設定を変更または確認できます。

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。

2. [フィッシング対策 **] ページで、[作成** ] をクリック **します**。

3. 新 **しいフィッシング対策ポリシーの作成ウィザードが** 開きます。 [ポリシー **に名前を付け] ページ** で、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[適用先** ] ページで、ポリシーが適用される内部受信者を特定します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

   [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用] の下の条件を **選択します**。

   - **受信者は、** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。
   - **受信者が次のメンバーである**: 組織内の 1 つ以上のグループを指定します。
   - **受信者ドメイン:** 組織内の構成済みの 1 つ以上の承認されたドメインの受信者を指定します。

   条件を選択すると、対応するドロップダウンが [Any **of these] ボックスと一緒に表示** されます。

   - ボックス内をクリックし、値の一覧をスクロールして選択します。
   - ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。
   - 値を追加するには、ボックス内の空の領域をクリックします。
   - 個々のエントリを削除するには、値の **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。
   - 条件全体を削除するには、条件の **[削除**] ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

   追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する条件] の下の残りの値 **を選択します**。

   例外を追加するには、[条件の追加] をクリックし、[条件以外] で例外 **を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[設定の確認** ] ページで、設定を確認します。 各設定で **[編集]** をクリックして変更できます。

   完了したら、[このポリシーの作成 **] をクリックします**。

6. 表示 **される確認ダイアログで [OK]** をクリックします。

これらの全般設定でフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを変更する

フィッシング対策ポリシー (作成した新しいポリシー、または既にカスタマイズした既存のポリシー) を変更するには、次の手順を使用します。

1. If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.

2. 変更するカスタムフィッシング詐欺対策ポリシーを選択します。 既に選択されている場合は、選択を解除して、もう一度選択します。

3. [**ポリシーの編集 \<name\> ]** フライアウトが表示されます。 任意の **セクションで [** 編集] をクリックすると、そのセクションの設定にアクセスできます。

   - 次の手順は、セクションが表示される順序で示されますが、順番には表示されません (セクションは任意の順序で選択および変更できます)。

   - セクションで [編集] をクリックすると、使用可能な設定がウィザード形式で表示されますが、任意の順序でページ内にジャンプできます。また、任意のページで [保存]  (または [キャンセル] または [閉じる] アイコン) をクリックしてポリシーの編集ページに戻ります ![ ](../../media/scc-remove-icon.png) (**\<name\>** 保存または終了するにはウィザードの最後のページにアクセスする必要はありません)。

4. **ポリシー設定**: [編集 **] を** クリックして、前の [](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365)セクションでポリシーを作成した場合と同じ設定を変更します。

   - **名前**
   - **説明**
   - **適用先**
   - **設定を確認する**

   完了したら、任意のページで [保存 **]** をクリックします。

5. **偽装 :**[編集 **]** をクリックして、ポリシー内の保護された送信者と保護されたドメインを変更します。 これらの設定は、受信メッセージの差出人アドレスでスプーフィングされた送信者が (個別に、またはドメインごとに) 探すポリシーの条件です。 詳細については、「Microsoft Defender for Office [365」](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)を参照してください。

   - **保護するユーザーを追加** する : 既定値は [オフ] **です**。 有効にする場合は、トグルを **[オン**] にスライドし、表示される **[ユーザー** の追加] ボタンをクリックします。

     表示される **[ユーザーの追加** ] フライアウトで、次の値を構成します。

     - **電子メール アドレス**:

       - ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。
       - ボックスをクリックし、入力を開始してリストをフィルター処理し、ユーザーを選択します。
       - エントリを削除するには、ユーザーの **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

     - **[** 名前]: この値は、選択したメール アドレスに基づいて設定されますが、変更できます。

     完了したら、任意のページで [保存 **]** をクリックします。

     既存のエントリを編集するには、一覧で保護されたユーザーを選択します。

     > [!NOTE]
     >
     > - 各フィッシング対策ポリシーでは、最大 60 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。 複数のポリシーで同じ保護されたユーザーを指定できない。
     >
     > - 送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。 送信者と受信者が電子メールで通信したことがない場合、メッセージは偽装の試行として識別されます。

   - **保護するドメインを追加** する : 次の設定の一方または両方を構成します。

     - **所有しているドメインを自動的に含める**: 既定値は [オフ] **です**。 オンに切り替えるには、トグルを [オン] に **スライドします**。
     - **カスタム ドメインを含める**: 既定値はオフ **です**。 有効にする場合は、トグルを **[オン**] にスライドし、[ドメインの追加] ボックスにドメイン名 (contoso.com など) を入力し、Enter キーを押して、必要に応じて繰り返します。

     > [!NOTE]
     > すべてのフィッシング対策ポリシーには、最大 50 のドメインを設定できます。

   - **Actions**: Click **Edit**

     - **偽装ユーザー** によって電子メールが送信される場合: 「保護するユーザーを追加する」で指定した保護されたユーザーの 1 つが、スプーフィングされた送信者であるメッセージに対して次のいずれかのアクションを **構成します**。

       - **アクションを適用しない**
       - **メッセージを他のメール アドレスにリダイレクトする**
       - **メッセージを [迷惑メール] フォルダーに移動する**
       - **メッセージを検疫する**
       - **メッセージを配信し、BCC 行に他のアドレスを追加する**
       - **配信前にメッセージを削除する**

     - **偽装された** ドメインによって電子メールが送信される場合: 「ドメインの追加」で指定した保護されたドメインの 1 つにスプーフィングされた送信者が含むメッセージに対して、次のいずれかのアクションを構成 **します**。

       - **アクションを適用しない**
       - **メッセージを他のメール アドレスにリダイレクトする**
       - **メッセージを [迷惑メール] フォルダーに移動する**
       - **メッセージを検疫する**
       - **メッセージを配信し、BCC 行に他のアドレスを追加する**
       - **配信前にメッセージを削除する**

   - [ **偽装の安全性に関するヒントをオンにする** ] をクリックし、次の設定を構成します。

     - **偽装したユーザーのヒントを表示** する : 既定値は **[オフ] です**。 オンに切り替えるには、トグルを [オン] に **スライドします**。
     - **偽装されたドメインのヒントを表示** する : 既定値は **[オフ] です**。 オンに切り替えるには、トグルを [オン] に **スライドします**。
     - **通常と異なっている文字のヒント** を表示する : 既定値は **オフです**。 オンに切り替えるには、トグルを [オン] に **スライドします**。

     完了したら、**[保存]** をクリックします。

   - **メールボックス インテリジェンス**:

     - **メールボックス インテリジェンスを有効にする:** 既定値は **[オン] です**。 オフに切り替えるには、トグルを [オフ] に **スライドします**。

     - **メールボックス インテリジェンス ベースの偽装保護を** 有効にする: この設定は、[メールボックス インテリジェンスを有効にする] がオンの場合 **にのみ** 使用 **できます**。

       In **If email is sent by an impersonated user,** you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):

       - **アクションを適用しない**
       - **メッセージを他のメール アドレスにリダイレクトする**
       - **メッセージを [迷惑メール] フォルダーに移動する**
       - **メッセージを検疫する**
       - **メッセージを配信し、BCC 行に他のアドレスを追加する**
       - **配信前にメッセージを削除する**

   - **信頼できる送信者とドメインを追加** する : ポリシーの例外を指定します。

     - **信頼できる送信者**:

       - ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。
       - ボックスをクリックし、入力を開始してリストをフィルター処理し、ユーザーを選択します。
       - エントリを削除するには、ユーザーの **[削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

     - **信頼されたドメイン**: ドメイン名 (たとえば、contoso.com) を入力し、Enter キーを押して、必要に応じて繰り返します。

   - **設定を確認** します。個々の手順をクリックする代わりに、設定が概要に表示されます。

     - 各セクションで **[編集]** をクリックすると、関連するページに戻ります。
     - このページでは、次の設定 **をオン** または **オフ** に直接切り替えます。

       - **保護されたユーザー**
       - **保護されたドメイン** \>**所有しているドメインを含める**
       - **保護されたドメイン** \>**保護されたドメイン**(カスタム ドメイン)
       - **メールボックス インテリジェンス**

   完了したら、任意のページで [保存 **]** をクリックします。

6. **ス** プーフィング : **[編集** ] をクリックしてスプーフィング インテリジェンスを有効またはオフにし、Outlook の認証されていない送信者の識別をオンまたはオフにし、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

   これらの設定は、EOP のフィッシング対策ポリシーでも使用できます。

   - **スプーフィング フィルターの** 設定 : 既定値は **[オン**] であり、オンのままにすることをお勧めします。 オフに切り替えるには、トグルを [オフ] に **スライドします**。 詳細については [、「EOP でスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング対策保護を無効にする必要があります。コネクタの拡張フィルターを有効にしてください。 手順については [、「Exchange Online のコネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **認証されていない送信者機能を有効** にする : 既定値は **[オン] です**。 オフに切り替えるには、トグルを [オフ] に **スライドします**。

   - **アクション**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。

     **ドメインのなりすましを許可されていないユーザーからメールが送信された場合**:

     - **受信者の迷惑メール フォルダーにメッセージを移動する**
     - **メッセージを検疫する**

   - **設定を確認** します。個々の手順をクリックする代わりに、設定が概要に表示されます。

     - 各セクションで **[編集]** をクリックすると、関連するページに戻ります。
     - このページでは、次の設定 **をオン** または **オフ** に直接切り替えます。
       - **スプーフ対策保護を有効にする**
       - **認証されていない送信者機能を有効にする**

   完了したら、任意のページで [保存 **]** をクリックします。

7. **[詳細設定]**: [ **編集]** をクリックして、高度なフィッシングしきい値を構成します。 詳細については、Microsoft Defender for Office [365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)のフィッシング対策ポリシーの高度なフィッシングしきい値を参照してください。

   - **高度なフィッシングのしきい値**: 次のいずれかの値を選択します。

   - **1 - 標準** (これは既定値です。
   - **2 - 積極的**
   - **3 - より積極的**
   - **4 - 最も積極的**

   - **設定を確認する**: [編集 **] を** クリックして、[高度なフィッシングのしきい値 **] ページに戻** ります。

   完了したら、いずれかのページで [保存 **]** をクリックします。

8. [ポリシーの編集 **] \<Name\> ページに戻** り、設定を確認し、[閉じる] をクリック **します**。

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 の既定のフィッシング対策ポリシーを変更する

microsoft Defender for Office 365 の既定のフィッシング対策ポリシーは Office365 AntiPhish Default という名前で、ポリシーの一覧には表示されません。 既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。

2. [フィッシング対策 **] ページで、[** 既定のポリシー] **をクリックします**。

3. [ **ポリシーの編集] の [Office365 AntiPhish Default] ページ** が表示されます。 以下のセクションを使用できます。カスタム ポリシーを変更する場合と同じ設定 [が含まれます](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)。

   - **偽装**
   - **スプーフィング**
   - **詳細設定**

   既定のポリシーを変更する場合、次の設定は使用できません。

   - [ポリシー設定]セクションと値を確認できますが、[編集]リンクは表示されません。そのため、設定 (ポリシー名、説明、およびポリシーが適用されるユーザー (すべての受信者に適用されます) を変更できない。
   - 既定のポリシーは削除できない。
   - 既定のポリシーの優先度は変更できない (常に最後に適用される)。

4. On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender でカスタムフィッシング対策ポリシーを有効または無効にする (Office 365)

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。

2. [状態] 列の値 **に注意** してください。

   - トグルを [ **オフ] にスライド** してポリシーを無効にします。

   - トグルを [ **オン] にスライドして** ポリシーを有効にします。

既定のフィッシング詐欺対策ポリシーを無効にできない。

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender でカスタムフィッシング対策ポリシーの優先度を設定する (Office 365)

既定では、フィッシング詐欺対策ポリシーには、作成された順序に基づく優先度が設定されます (新しいポリシーは、古いポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

カスタムフィッシング詐欺対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** の値は 0 です)。 Office365 AntiPhish Default という名前の既定のフィッシング詐欺対策ポリシーにはカスタムの優先度値 **Lowest** が設定されています。この値は変更できます。

 **注**: セキュリティ & コンプライアンス センターでは、フィッシング対策ポリシーを作成した後にのみ、優先度を変更できます。 PowerShell では、フィッシング対策ルールの作成時に既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、ポリシーのプロパティで [優先度の引き上げ] または [優先度の下げ]をクリックします (セキュリティ/コンプライアンス センターで優先度番号を直接変更&することはできません)。  ポリシーの優先度の変更は、複数のポリシーがある場合にのみ有効です。

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。

2. 変更するポリシーを選択します。 既に選択されている場合は、選択を解除して、もう一度選択します。

3. [**ポリシーの編集 \<name\> ]** フライアウトが表示されます。

   - 優先度の値が **0** のカスタムフィッシング詐欺対策ポリシーでは、[優先度の下がり]**ボタンしか** 使用できません。

   - 優先度の値が最も低いカスタムフィッシング詐欺対策ポリシー (**たとえば、3)** では、[優先度の引き上げ]**ボタンしか使用** できません。

   - 3 つ以上のカスタムフィッシング詐欺対策ポリシーがある場合は、優先度の高い値と最も低い値の間のポリシーの [優先度の引き上げ] ボタンと [優先度の下げ] ボタンの両方を使用できます。

4. [優先度 **の引き上げ** ] または **[優先度の下げ** ] をクリックして、[優先度] の **値を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを表示する

1. セキュリティ/コンプライアンス センター&、脅威 **管理** ポリシー ATP のフィッシング対策 \>  \> **に移動します**。

2. 次のいずれかの手順を実行します。

   - 表示するカスタムフィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除して、もう一度選択します。

   - 既定 **のフィッシング** 対策ポリシーを表示するには、[既定のポリシー] をクリックします。

3. [**ポリシーの編集 \<name\> ]** フライアウトが表示され、設定と値を表示できます。

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>セキュリティ/コンプライアンス センター&使用して、Microsoft Defender for Office 365 のフィッシング対策ポリシーを削除する

1. セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。

2. 削除するポリシーを選択します。 既に選択されている場合は、選択を解除して、もう一度選択します。

3. 表示される **[ポリシー \<name\> の** 編集] フライアウトで、[ポリシーの削除]をクリックし、表示される警告ダイアログで [はい] をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Exchange Online PowerShell を使用して Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)

前述のように、スパム対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されます。

Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明白です。 **\* -AntiPhishPolicy** コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。

- PowerShell では、最初にフィッシング対策ポリシーを作成し、次に、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。
- PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。
- PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。

1. フィッシング対策ポリシーを作成します。
2. ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。

 **注**:

- 新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。 フィッシング詐欺対策ルールは、複数のフィッシング対策ポリシーに関連付けらなけな。

- ポリシーを作成するまで、セキュリティ/コンプライアンス センターで使用できない新しいフィッシング詐欺対策ポリシーに関する次の設定を構成&できます。

  - 新しいポリシーを無効な状態 _で作成_ `$false` します **(New-AntiPhishRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-AntiPhishRule** コマンドレットで、作成時のポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しいフィッシング対策ポリシーは、そのポリシーをフィッシング対策ルールに割り当てるまで、セキュリティ & コンプライアンス センターに表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する

フィッシング対策ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。

- ポリシーは有効です _(Enabled_ パラメーターは使用しません。既定値は有効です `$true` )。
- 説明は、リサーチ部門のポリシーです。
- すべての承認されたドメインに対する組織ドメインの保護と、組織のドメインに対する対象ドメインfabrikam.com。
- 偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。
- メールボックスのインテリジェンスを有効にします。
- メールボックス インテリジェンス保護を有効にし、検疫アクションを指定します。
- 安全性のヒントを有効にする。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

構文およびパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>手順 2: PowerShell を使用してフィッシング対策ルールを作成する

フィッシング対策ルールを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の条件で Research Department という名前のフィッシング対策ルールを作成します。

- ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられている。
- ルールは Research Department という名前のグループのメンバーに適用されます。
- _Priority_ パラメーターを使用していないので、既定の優先度が使用されます。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

構文およびパラメーターの詳細については [、「New-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを表示する

既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと一緒に、すべてのフィッシング対策ポリシーの要約リストを返します。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

構文およびパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを表示する

既存のフィッシング対策ルールを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと一緒に、すべてのフィッシング対策ルールの要約リストを返します。

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

構文およびパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを変更する

次の項目以外に、PowerShell でフィッシング対策ポリシーを変更する場合も、「手順 [1: PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) を使用してフィッシング詐欺対策ポリシーを作成する」セクションで説明したように、PowerShell でフィッシング対策ポリシーを変更する場合と同じ設定を使用できます。

- 指定したポリシーを既定のポリシー (すべてのユーザーに適用され、常に最も低い優先度に適用され、削除できない) に変える _MakeDefault_ スイッチは、PowerShell でフィッシング対策ポリシーを変更した場合にのみ使用できます。

- フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。 セキュリティ/コンプライアンス センターでフィッシング詐欺対策ポリシーの名前を変更&、フィッシング対策ルールの名前 _を変更する_ のみです。

フィッシング対策ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを変更する

PowerShell でフィッシング対策ルールを変更する場合に使用できない唯一の設定は、無効なルールを作成できる _Enabled_ パラメーターです。 既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、PowerShell でフィッシング対策ルールを変更するときに追加の設定を使用できません。 「手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用してフィッシング対策ルールを作成する」セクションで説明したように、ルールを作成する場合と同じ設定を使用できます。

フィッシング対策ルールを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを有効または無効にする

PowerShell でフィッシング対策ルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシング対策ルールと割り当てられたフィッシング対策ポリシー) が有効または無効にされます。 既定のフィッシング詐欺対策ポリシーを有効または無効にできない (常にすべての受信者に適用される)。

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

構文およびパラメーターの詳細については [、「Enable-AntiPhishRule」](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) および [「Disable-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell でフィッシング対策ルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注**:

- 新しいルールを作成するときに優先度を設定するには、代わりに **New-AntiPhishRule** コマンドレットの _Priority_ パラメーターを使用します。

- 既定のフィッシング対策ポリシーには対応するフィッシング対策ルールが設定されていないので、常に変更できない優先度の値 **が Lowest です**。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを削除する

PowerShell を使用してフィッシング対策ポリシーを削除する場合、対応するフィッシング対策ルールは削除されません。

PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを削除する

PowerShell を使用してフィッシング対策ルールを削除する場合、対応するフィッシング対策ポリシーは削除されません。

PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ルールを削除します。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、「Remove-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

Office 365 用に Microsoft Defender でフィッシング対策ポリシーが正常に構成されたことを確認するには、次の手順を実行します。

- セキュリティ/コンプライアンス センター&、**脅威管理ポリシー** ATP のフィッシング対策 \>  \> **に移動します**。 ポリシーの一覧、状態の値、 **および優先度** の値を **確認** します。 詳細を表示するには、次のいずれかの手順を実行します。

  - 一覧からポリシーを選択し、詳細をフライアウトで表示します。
  - [ **既定のポリシー]** をクリックし、詳細をフライアウトに表示します。

- Exchange Online PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを実行して \<Name\> 設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
