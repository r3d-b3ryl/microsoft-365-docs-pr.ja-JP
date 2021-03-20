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
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスを持つ組織または Exchange Online メールボックスを使用しない組織で使用できるフィッシング対策ポリシーを作成、変更、および削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 945c993c32d6258fc4d9a9edd51b9ed7e8f64c37
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906602"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>EOP でのスパム対策ポリシーの構成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)

Exchange Online または Exchange Online メールボックスのないスタンドアロン Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、既定で有効になっているスプーフィング対策機能の数が制限されている既定のフィッシング対策ポリシーがあります。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

管理者は、既定のフィッシング対策ポリシーを表示、編集、および構成できます (ただし、削除はされません)。 さらに細分化するために、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムフィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

Exchange Online メールボックスを持つ組織は、セキュリティ コンプライアンス センターまたは Exchange Online PowerShell &フィッシング対策ポリシーを構成できます。 スタンドアロン EOP 組織は、コンプライアンス センター&使用できます。

Office 365 の Defender で使用できる Microsoft Defender for Office 365 のより高度なフィッシング対策ポリシーを作成および変更する方法については、「Configure anti-フィッシング ポリシー in [Microsoft Defender for Office 365」](configure-atp-anti-phishing-policies.md)を参照してください。

フィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシング対策ポリシー**: 有効または無効にするフィッシング保護と、オプションを適用するアクションを指定します。
- **フィッシング対策ルール**: フィッシング対策ポリシーの優先度と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

これらの 2 つの要素の違いは、セキュリティ コンプライアンス センターでフィッシング対策ポリシーを管理&ではありません。

- フィッシング対策ポリシーを作成する場合は、両方に同じ名前を使用して、実際にフィッシング対策ルールと関連付けられたフィッシング対策ポリシーを同時に作成します。
- フィッシング対策ポリシーを変更すると、名前、優先度、有効または無効、および受信者フィルターに関連する設定によって、フィッシング対策ルールが変更されます。 その他の設定はすべて、関連付けられたフィッシング対策ポリシーを変更します。
- フィッシング対策ポリシーを削除すると、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが削除されます。

Exchange Online PowerShell では、ポリシーとルールを個別に管理します。 詳細については、この記事の後半にある [「Exchange Online PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies) を使用してフィッシング対策ポリシーを構成する」セクションを参照してください。

すべての組織には、次のプロパティを持つ Office365 AntiPhish Default という名前の組み込みのフィッシング対策ポリシーがあります。

- ポリシーは、ポリシーに関連付けられたフィッシング対策ルール (受信者フィルター) がない場合でも、組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

フィッシング対策保護の効果を高めるには、特定のユーザーまたはユーザー グループに適用されるより厳しい設定で、カスタムのフィッシング対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 フィッシング対策ページに直接 **移動するには** 、 を使用します <https://protection.office.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

  スタンドアロン EOP PowerShell ではフィッシング対策ポリシーを管理できない。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - フィッシング対策ポリシーを追加、変更、削除するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - フィッシング対策ポリシーへの読み取り専用アクセスには、グローバル リーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります <sup>\*</sup> 。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) **の [組織の管理の** 表示のみ] 役割グループは、この機能への読み取り専用アクセスも提供します <sup>\*</sup> 。
  - <sup>\*</sup> セキュリティ コンプライアンス センター&読み取り専用アクセスを使用すると、ユーザーはカスタムフィッシング対策ポリシーの設定を表示できます。 読み取り専用のユーザーは、既定のフィッシング対策ポリシーの設定を表示できます。

- スタンドアロン EOP でフィッシング対策ポリシーを作成および変更するには、テナントに水和が必要な _操作を行う_ 必要があります。 たとえば、Exchange 管理センター (EAC) で、[アクセス許可]タブに移動し、既存の役割グループを選択し、[編集] アイコンをクリックし、役割を削除します (最終的に追加し戻します ![ ](../../media/ITPro-EAC-EditIcon.png) )。 テナントが水和されたことがない場合は、[組織の設定の更新] という名前のダイアログが表示され、進行状況バーが表示され、正常に完了します。 ハイドレーションの詳細については [、「Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) コマンドレット (スタンドアロン EOP PowerShell またはセキュリティ & コンプライアンス センターでは使用できません)」を参照してください。

- フィッシング対策ポリシーの推奨設定については、「EOP の既定のフィッシング対策 [ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

- 更新されたポリシーを適用するには、最大 30 分かかります。

- フィルター 処理パイプラインでフィッシング対策ポリシーが適用される場所については、「メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>コンプライアンス センター&を使用してフィッシング対策ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタムフィッシング対策ポリシーを作成すると、両方に同じ名前を使用して、フィッシング対策ルールと関連付けられたフィッシング対策ポリシーが同時に作成されます。

フィッシング対策ポリシーを作成する場合、ポリシーの名前、説明、およびポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。 ポリシーを作成した後、ポリシーを変更して、既定のフィッシング対策設定を変更または確認できます。

1. [セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。

2. [フィッシング **対策] ページで、[作成** ] を **クリックします**。

3. [ **新しいフィッシング対策ポリシーの作成] ウィザードが** 開きます。 [ポリシーに **名前を付け] ページ** で、次の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **[適用先]** ページで、ポリシーが適用される内部受信者を特定します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

   [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用する場合] で条件 **を選択します**。

   - **受信者は:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。
   - **受信者は: のメンバーです**。組織内の 1 つ以上のグループを指定します。
   - **[受信者のドメインが次の値である]**: 組織内で構成済みの 1 つ以上の承認済みドメイン内の受信者を指定します。

   条件を選択すると、対応するドロップダウンが [Any of **these] ボックスと一緒に表示** されます。

   - ボックス内をクリックし、値の一覧をスクロールして選択します。
   - ボックス内をクリックし、入力を開始してリストをフィルター処理し、値を選択します。
   - 追加の値を追加するには、ボックス内の空の領域をクリックします。
   - 個々のエントリを削除するには、値 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。
   - 条件全体を削除するには、条件 **の [削除]** ![ ](../../media/scc-remove-icon.png) アイコンをクリックします。

   追加の条件を追加するには、[条件の追加] **をクリックし** 、[適用する場合] で残りの値 **を選択します**。

   例外を追加するには、[条件の追加] **をクリックし** 、[条件を除く] で例外 **を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. 表示される **[設定の確認]** ページで、設定を確認します。 各設定で **[編集]** をクリックして変更できます。

   完了したら、[このポリシーの作成 **] をクリックします**。

6. 表示 **される確認ダイアログで [OK]** をクリックします。

これらの一般的なポリシー設定を使用してフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>セキュリティ コンプライアンス センターを&フィッシング対策ポリシーを変更する

フィッシング対策ポリシー (作成した新しいポリシー、または既にカスタマイズした既存のポリシー) を変更するには、次の手順を使用します。

1. まだインストールされていない場合は、セキュリティ & コンプライアンス センターを開き、[脅威管理ポリシーのフィッシング対策] \>  \> **に移動します**。

2. 変更するカスタムフィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. [**ポリシーの編集 \<name\> ] フライ** アウトが表示されます。 任意の **セクションで [** 編集] をクリックすると、そのセクションの設定にアクセスできます。

   - 次の手順は、セクションが表示される順序で示されますが、順番に表示されません (任意の順序でセクションを選択および変更できます)。

   - セクションで[編集] をクリックすると、使用可能な設定はウィザード形式で表示されますが、任意の順序でページ内に移動できます。任意のページで [保存]  ( ![ ](../../media/scc-remove-icon.png) **\<name\>** または [キャンセル] または [閉じる] アイコンをクリックして [ポリシーの編集] ページに戻ります (ウィザードの最後のページにアクセスして保存または終了する必要はありません)。

4. **ポリシー設定**: [ **編集]** をクリックして、前のセクションでポリシーを作成した場合と同じ [設定を変更](#use-the-security--compliance-center-to-create-anti-phishing-policies) します。

   - **名前**
   - **説明**
   - **適用先**
   - **設定を確認する**

   完了したら、任意のページで **[保存]** をクリックします。

5. **ス** プーフィング : **[編集** ] をクリックしてスプーフィング インテリジェンスをオンまたはオフにし、Outlook で認証されていない送信者 ID をオンまたはオフにし、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。 詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

   これらの同じ設定は、Defender for Office 365 のフィッシング対策ポリシーでも使用できます。

   - **スプーフィング フィルターの** 設定 : 既定値は **On** で、オンのままにすることをお勧めします。 オフにする場合は、トグルを [オフ] に **スライドします**。 詳細については [、「EOP でスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング防止保護を無効にする必要があります。代わりに、コネクタの拡張フィルターを有効にできます。 手順については [、「Enhanced Filtering for Connectors in Exchange Online」を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **認証されていない送信者機能を有効にする**: 既定値は On **です**。 オフにする場合は、トグルを [オフ] に **スライドします**。

   - **Actions**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。

     **ドメインのスプーフィングが許可されていない** ユーザーからメールが送信された場合:

     - **受信者の迷惑メール フォルダーにメッセージを移動する**
     - **メッセージを検疫する**

   - **設定を確認する**: 個々の手順をクリックする代わりに、設定が概要に表示されます。

     - 各セクションで **[編集]** をクリックすると、関連するページに戻ります。
     - このページでは、次の設定 **をオン** または **オフに** 直接切り替えます。

       - **スパム対策の保護を有効にする**
       - **認証されていない送信者機能を有効にする**

   完了したら、任意のページで **[保存]** をクリックします。

6. [ポリシーの編集 **] \<Name\> ページに戻り**、設定を確認し、[閉じる] を **クリックします**。

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>既定のフィッシング&ポリシーを変更するには、セキュリティ コンプライアンス センターを使用します。

既定のフィッシング対策ポリシーは Office365 AntiPhish Default という名前で、ポリシーの一覧には表示されません。 既定のフィッシング対策ポリシーを変更するには、次の手順を実行します。

1. [セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。

2. [フィッシング **対策] ページで、[** 既定のポリシー] **をクリックします**。

3. [ **ポリシーの編集] [Office365 AntiPhish Default] ページ** が表示されます。 カスタム ポリシーを変更する場合と同じ設定を含む、次の [セクションを使用できます](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。

   - **偽装**
   - **スプーフィング**
   - **詳細設定**

   既定のポリシーを変更すると、次の設定を使用できません。

   - [ポリシーの設定] セクションと値を確認できますが、[編集]リンクはないので、設定 (ポリシー名、説明、ポリシーが適用されるユーザー (すべての受信者に適用されます) を変更できます)。
   - 既定のポリシーを削除できない。
   - 既定のポリシーの優先度は変更できない (常に最後に適用されます)。

4. [ポリシー **の編集] [Office365 AntiPhish Default]** ページで、設定を確認し、[閉じる] を **クリックします**。

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーを有効または無効にする

1. [セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。

2. [状態] 列の値 **に注意** してください。

   - トグルを [オフ] **にスライドして** ポリシーを無効にします。

   - トグルを [オン] **にスライドして** ポリシーを有効にします。

既定のフィッシング対策ポリシーを無効にできない。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>カスタムフィッシング対策ポリシーの優先度を設定する

既定では、フィッシング対策ポリシーには、作成された順序に基づく優先度が与えられる (新しいポリシーは、以前のポリシーよりも優先度が低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

カスタムフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** は 0 です)。 Office365 AntiPhish Default という名前の既定のフィッシング対策ポリシーには、カスタム優先度の値 **が [** 最低] であり、変更できない。

 **注**: セキュリティ & コンプライアンス センターでは、フィッシング対策ポリシーを作成した後にのみ優先度を変更できます。 PowerShell では、フィッシング対策ルールを作成するときに既定の優先度を上書きできます (既存のルールの優先度に影響を与える可能性があります)。

ポリシーの優先度を変更するには、ポリシーのプロパティで [優先度の引き上げ] または [優先度の下げ]をクリックします (セキュリティ & コンプライアンス センターで優先度番号を直接変更することはできません)。  ポリシーの優先度を変更すると、複数のポリシーがある場合にのみ有効です。

1. [セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** ] ATP の \>  \> **フィッシング対策に移動します**。

2. 変更するポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. [**ポリシーの編集 \<name\> ] フライ** アウトが表示されます。

   - 優先度の値が **0** のカスタムフィッシング対策ポリシーには、[優先度の下がり]**ボタンしか** 使用できません。

   - 優先度の値が最も低いカスタムフィッシング対策ポリシー (**たとえば、3)** には、[優先度の引き上げ]**ボタン** しか使用できません。

   - 3 つ以上のカスタムフィッシング対策ポリシーがある場合、優先度の最も高い値と最も低い値の間のポリシーには、[優先度の引き上げ] ボタンと [優先度の下げ] ボタンの **両方が用意** されています。

4. [優先度 **の増加] または** **[優先度の下げ** ] をクリックして、 **優先度の値を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>セキュリティ コンプライアンス センター&フィッシング対策ポリシーを表示する

1. [セキュリティ & コンプライアンス センター] で、[脅威 **管理ポリシー** のフィッシング対策 \>  \> **] に移動します**。

2. 次のいずれかの手順を実行します。

   - 表示するカスタムフィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

   - [既定 **のポリシー]** をクリックして、既定のフィッシング対策ポリシーを表示します。

3. [**ポリシーの編集 \<name\> ] フライ** アウトが表示され、設定と値を表示できます。

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>セキュリティ コンプライアンス センター&フィッシング対策ポリシーを削除する

1. [セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。

2. 削除するポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. 表示される **[ポリシー \<name\> の編集]** フライアウトで、[ポリシーの削除] をクリックし、表示される警告ダイアログで [**は** い] をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell を使用してフィッシング対策ポリシーを構成する

前述したように、フィッシング対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されています。

Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いが明らかです。 -AntiPhishPolicy コマンドレットを使用してフィッシング対策ポリシーを管理し **\* 、-AntiPhishRule** コマンドレットを使用してフィッシング対策ルールを管理します。 **\***

- PowerShell では、最初にフィッシング対策ポリシーを作成してから、そのルールが適用されるポリシーを識別するフィッシング対策ルールを作成します。
- PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定を個別に変更します。
- PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動的には削除されません。その逆も同様です。

> [!NOTE]
> 次の PowerShell 手順は、Exchange Online Protection PowerShell を使用するスタンドアロン EOP 組織では使用できません。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell でフィッシング対策ポリシーを作成するには、次の 2 つの手順を実行します。

1. フィッシング対策ポリシーを作成します。
2. ルールが適用されるフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。

 **注**:

- 新しいフィッシング対策ルールを作成し、関連付けされていない既存のフィッシング対策ポリシーを割り当てできます。 フィッシング対策ルールを複数のフィッシング対策ポリシーに関連付けできない。

- ポリシーを作成するまで、セキュリティ & コンプライアンス センターで使用できない PowerShell の新しいフィッシング対策ポリシーで、次の設定を構成できます。

  - 無効として新しいポリシーを作成 _します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。
  -  _\<Number\>_ **New-AntiPhishRule** コマンドレットの作成時にポリシーの優先度 (優先度) を設定します。

- PowerShell で作成した新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策ルールに割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する

フィッシング対策ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

この例では、次の設定を使用して、Research Quarantine という名前のフィッシング対策ポリシーを作成します。

- 説明は、調査部門のポリシーです。
- スプーフィングの既定のアクションを [検疫] に変更します。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

構文とパラメーターの詳細については [、「New-AntiPhishPolicy」を参照してください](/powershell/module/exchange/New-AntiPhishPolicy)。

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

- フィッシング対策ポリシーの名前を変更することはできません **(Set-AntiPhishPolicy** コマンドレットには _Name_ パラメーターはありません)。 セキュリティ & コンプライアンス センターでフィッシング対策ポリシーの名前を変更すると、フィッシング対策ルールの名前が変更 _されます_。

フィッシング対策ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文とパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](/powershell/module/exchange/Set-AntiPhishPolicy)。

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

Microsoft Defender for Office 365 でフィッシング対策ポリシーが正常に構成されたことを確認するには、次の手順を実行します。

- [セキュリティ & コンプライアンス センター] で、[**脅威管理ポリシー** のフィッシング \>  \> **対策] に移動します**。 ポリシー、その状態の値、および **優先度** の値の一覧を **確認** します。 詳細を表示するには、次のいずれかの手順を実行します。

  - 一覧からポリシーを選択し、詳細をフライアウトで表示します。
  - [既定 **のポリシー] を** クリックし、詳細をフライアウトで表示します。

- Exchange Online PowerShell で、ポリシーまたはルールの名前に置き換え、次のコマンドを \<Name\> 実行し、設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```