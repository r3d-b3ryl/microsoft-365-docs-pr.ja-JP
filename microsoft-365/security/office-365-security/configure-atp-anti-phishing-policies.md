---
title: ATP フィッシング詐欺対策ポリシーを設定する
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
description: 管理者は、Office 365 Advanced Threat Protection (Office 365 ATP) を使用して組織で使用可能な高度なフィッシング対策ポリシーを作成、変更、削除する方法について説明します。
ms.openlocfilehash: f7770945e6b99a3d2f3fa2b12daa13b2cc3c2612
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825739"
---
# <a name="configure-atp-anti-phishing-policies"></a>ATP フィッシング詐欺対策ポリシーを設定する

ATP フィッシング対策ポリシーは [、365 Advanced Threat Protection Officeの一部です](office-365-atp.md)。 ATP フィッシング対策ポリシーは、悪意のある偽装ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護することができます。 Exchange Online Protection (EOP) と ATP フィッシング対策ポリシーの違いの詳細については、「フィッシング対策 [保護」を参照してください](anti-phishing-protection.md)。

管理者は、既定の ATP フィッシング対策ポリシーを表示、編集、構成できます (削除することはできません)。 よりきめ細かく計画する場合は、組織内の特定のユーザー、グループ、またはドメインに適用される、カスタム ATP フィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

ATP のフィッシング対策ポリシーは、セキュリティ コンプライアンス & Exchange Online PowerShell で構成できます。

Exchange Online Protection 組織で使用可能なフィッシング対策ポリシーの構成 (つまり、Office 365 ATP を使用しない Microsoft 365 組織) の詳細については、「EOP でフィッシング対策 [ポリシーを構成する」を参照してください](configure-anti-phishing-policies-eop.md)。

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>セキュリティ センターと PowerShell の ATP & フィッシング対策ポリシー

ATP フィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシング対策ポリシー**: 有効化/無効化するフィッシング対策と、オプションを適用するアクションを指定します。
- **フィッシング対策ルール**: フィッシング対策ポリシーの優先順位と受信者フィルター (ポリシーが適用される対象者) を指定します。

これら 2 つの要素の違いは、セキュリティ/コンプライアンス センターで ATP のフィッシング対策ポリシーを管理する際には分 &いません。

- ポリシーを作成する場合、実際にはフィッシング対策ルールと、関連するフィッシング対策ポリシーの両方に同じ名前を使用して同時に作成します。
- ポリシーを変更すると、名前、優先順位、有効/無効、および受信者フィルターに関連する設定はフィッシング対策ルールを変更します。 その他のすべての設定は、関連付けられているフィッシング対策ポリシーを変更します。
- ポリシーを削除すると、フィッシング対策ルールと、関連付けられているフィッシング対策ポリシーが削除されます。

Exchange Online PowerShell では、ポリシーとルールを個別に管理します。 詳細については、このトピックで後述する [「Exchange Online PowerShell を使用して ATP フ](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) ィッシング対策ポリシー」セクションを構成する」を参照してください。

Office 365 ATP の組織には、Office365 AntiPhish Default という名前の組み込みの ATP フィッシング対策ポリシーがあります。このポリシーには、次のプロパティがあります。

- ポリシーと関連付けられているフィッシング対策ルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー (**IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

フィッシング対策保護の効果を高むには、特定のユーザーまたはユーザー グループに適用される、高い設定を持つカスタム ATP フィッシング対策ポリシーを作成できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 ATP フィッシ **ング対策ページに直接移動するには** 、次の手順を使用します <https://protection.office.com/antiphishing> 。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - ATP フィッシング対策ポリシーを追加、変更、および削除するには、次の役割グループのいずれかのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - ATP フィッシング対策ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- ATP フィッシング対策ポリシーに推奨される設定については [、「ATP フィッシング対策Officeのポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。

- 新しいポリシーまたは更新されたポリシーの適用を最大 30 分間許可します。

- フィルター パイプライン内でのフィッシング対策ポリシーの適用場所については、「 [メール保護の順序と優先順位」を参照してください](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>セキュリティ コンプライアンス センターを&、ATP フィッシング対策ポリシーを作成する

セキュリティ & コンプライアンス センターでカスタム ATP フィッシング対策ポリシーを作成すると、フィッシング対策ルールと関連するフィッシング対策ポリシーが両方に対して同じ名前を使用して同時に作成されます。

ATP フィッシング対策ポリシーを作成する場合、ポリシーの名前、説明、ポリシーが適用されるユーザーを識別する受信者フィルターのみを指定できます。 ポリシーを作成した後は、ポリシーを変更して既定のフィッシング対策設定を変更または確認できます。

1. コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。

2. [フ **ィッシング対策] ページで、[作成** ] を **クリックします**。

3. 新 **しいフィッシング対策ポリシーの作成ウィザード** が開きます。 [ポリシー **に名前を付けた** らす] ページで、以下の設定を構成します。

   - **[名前]**: わかりやすい一意のポリシー名を入力します。

   - **[説明]**: ポリシーについての説明を入力します (オプション)。

   完了したら、**[次へ]** をクリックします。

4. 表示される **ページに** [適用] ページで、ポリシーが適用される内部の受信者を識別します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

   [条件 **の追加] をクリックします**。 表示されるドロップダウンで、[適用する条件: **Applied if**

   - **受信者は次の場所**に、組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先を指定します。
   - **受信者が次のメンバーの場合**: 組織内の 1 つまたは複数のグループを指定します。
   - **受信者のドメインが**、組織内で構成されている承認済みドメインの 1 つ以上に含まれます。

   条件を選択すると、これらのボックスが見つかり、対応する **ドロップダウンが表示** されます。

   - ボックス内をクリックし、選択する値のリストをスクロールします。
   - ボックスをクリックし、入力してリストをフィルター処理し、値を選択します。
   - 値を追加するには、ボックス内の空の領域をクリックします。
   - 個々のエントリを削除するには、値 **の [削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。
   - 条件全体を削除するには、条件の [ **削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。

   条件をさらに追加するには、条件を **追加し、[適用する場合** は残りの値 **] を選択します**。

   例外を追加するには、[条件を **追加] をクリックし、[** 次の場合を除く] の下 **で例外を選択します**。 設定と動作は、条件とまったく同じです。

   完了したら、**[次へ]** をクリックします。

5. 表示される **設定の確認** ページで設定を確認します。 各設定で [ **編集** ] をクリックすると、変更できます。

   完了したら、[このポリシーの作成] **をクリックします**。

6. 表示された確認ダイアログで **[OK]** をクリックします。

これらの一般的なポリシー設定で ATP フィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>セキュリティ センター ポリシーを&、ATP フィッシング対策ポリシーを変更する

作成した新しいポリシー、または既にカスタマイズした既存のポリシーの ATP フィッシング対策ポリシーを変更するには、次の手順を使用します。

1. セキュリティ センターを開いていない場合は、セキュリティ コンプライアンス センターを開&、 **脅威管理** \> **ポリシー** \> **ATP フィッシング対策に移動します**。

2. 変更するカスタム ATP フィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. [**ポリシーの編集 \<name\> ]** ポップアップが表示されます。 いずれかの **セクション** で [編集] をクリックすると、そのセクションの設定にアクセスできます。

   - 次の手順は、セクションが表示される順番で示されますが、順番に説明しません (セクションは任意の順序で選択および変更できます)。

   - セクションで [**編集]** をクリックすると、使用できる設定がウィザード形式で表示されますが、任意の順序でページ内に移動できます。任意のページで**Save**[保存] または [**Close**閉じる] をクリックすると、[**ポリシー**の編集] ページに ![ 戻 ](../../media/scc-remove-icon.png) **ることができます \<name\> **(保存したり、そのまま中に行う必要はありません)。

4. **ポリシー設定**: 前 **のセクション** でポリシーを作成した際に使用できていたのと同 [じ設定を変更するには](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) 、[編集] をクリックします。

   - **名前**
   - **説明**
   - **適用先**
   - **設定の確認**

   完了したら、[任意のページで保存 **]** をクリックします。

5. **偽装:**[ **編集] をクリック** して、ポリシー内の保護対象の送信者と保護ドメインを変更します。 これらの設定は、スプーフィングされた送信者が受信メッセージの差出人アドレスで検索対象 (個別またはドメイン単位) を識別するポリシーの条件です。 詳細については [、ATP フィッシング対策ポリシーの偽装設定に関する記事を参照してください](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)。

   - **保護するユーザーを追加**します: 既定値は **Off です**。 オンにするには、トグルを **オン**にスライドして、表示される **[Add user]** ボタンをクリックします。

     表示される **[ユーザーを追加** ] ポップアップで、次の値を構成します。

     - **Email address**:

        - ボックス内をクリックし、選択するユーザーの一覧をスクロールします。
        - ボックスをクリックし、入力してリストをフィルター処理し、ユーザーを選択します。
        - エントリを削除するには、ユーザーの **[削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。

     - **Name:** この値は選択したメール アドレスに基づいて設定されますが、変更できます。

     完了したら、[任意のページで保存 **]** をクリックします。

    既存のエントリを編集するには、一覧で保護されたユーザーを選択します。

   - **保護するドメインを追加**します。次の設定の一方または両方を構成します。

     - **自動的に自分のドメインを含**め: 既定値は **Off です**。 オンにするには、トグルを On に切り替 **えなをスライドします**。
     - **カスタム ドメインを含**む: 既定値は **Off です**。 トグルをオンにスライドして **オンに**し、[ドメインの追加 **] ボックス** にドメイン名 (例: contoso.com) を入力し、Enter キーを押して必要に応じて繰り返します。

   - **操作**: [編集] **をクリックします**

     - **偽装されたユーザーによって電子メールが送信されている場合**: 偽装された送信者が保護対象のユーザーを追加する場合に指定した保護されたユーザーの 1 人であるメッセージに対して、 **次のいずれかの操作を構成します**。

       - **アクションを適用しない**
       - **他の電子メール アドレスへのメッセージのリダイレクト**
       - **迷惑メール フォルダーにメッセージを移動する**
       - **メッセージを検疫する**
       - **メッセージを配信して、他のアドレスを BCC 行に追加する**
       - **配信される前にメッセージを削除する**

     - **偽装ドメインによってメールが送信されている場合**: 保護対象のドメインに指定した保護されたドメインのいずれかに、スプーフィングされた送信者が、次のいずれかの **アクションを実行します**。

     - **アクションを適用しない**
     - **他の電子メール アドレスへのメッセージのリダイレクト**
     - **迷惑メール フォルダーにメッセージを移動する**
     - **メッセージを検疫する**
     - **メッセージを配信して、他のアドレスを BCC 行に追加する**
     - **配信される前にメッセージを削除する**

   - 偽 **装の安全のヒントを有効にし、** 次の設定を構成します。

     - **偽装ユーザーのヒントを表示します**。既定値は **"オフ**" です。 オンにするには、トグルを On に切り替 **えなをスライドします**。
     - **偽装ドメインのヒントを表示**: 既定値は **"オフ**" です。 オンにするには、トグルを On に切り替 **えなをスライドします**。
     - **通常使いない文字のヒントを**表示: 既定値は **Off です**。 オンにするには、トグルを On に切り替 **えなをスライドします**。

     完了したら、**[保存]** をクリックします。

   - **メールボックス インテリジェンス**:

     - **メールボックスのインテリジェンスを有効にしますか?:** 既定値は **On**です。 オンにするには、トグルをオフに切り替 **えます**。

     - **メールボックス インテリジェンス ベース偽装保護を有効にしますか?:** この設定は、メールボックス インテリジェンス **を有効にする場合にのみ使用できますか?** **オン**はオン

       偽 **装されたユーザーによって電子メールが送信された場合は、** 次のいずれかのアクションを、メールボックス インテリジェンス障害 (保護されたユーザーや保護されたドメインに対して実行可能なアクションと同じ操作) に対して実行する処理を指定できます。

       - **アクションを適用しない**
       - **他の電子メール アドレスへのメッセージのリダイレクト**
       - **迷惑メール フォルダーにメッセージを移動する**
       - **メッセージを検疫する**
       - **メッセージを配信して、他のアドレスを BCC 行に追加する**
       - **配信される前にメッセージを削除する**

   - **信頼できる送信者とドメインの追加**: ポリシーの例外を指定します。

     - **信頼できる送信者**:

       - ボックス内をクリックし、選択するユーザーの一覧をスクロールします。
       - ボックスをクリックし、入力してリストをフィルター処理し、ユーザーを選択します。
       - エントリを削除するには、ユーザーの **[削除** ![ ] ](../../media/scc-remove-icon.png) アイコンをクリックします。

     - **信頼できるドメイン**: ドメイン名 (例: contoso.com) を入力し、Enter キーを押して、必要に応じて繰り返します。

   - **設定を確認**します。個々の手順をクリックする代わりに、設定が概要に表示されます。

     - 各セクションで **[編集** ] をクリックすると、関連するページに戻ります。
     - 次の設定は、このページ **で直接 [オン** ] **または [オフ** ] に切り替えることができます。

       - **保護されたユーザー**
       - **保護されたドメイン** \>**所有するドメインを含む**
       - **保護されたドメイン** \>**保護されたドメイン**(カスタム ドメイン)
       - **メールボックス インテリジェンス**

   完了したら、[任意のページで保存 **]** をクリックします。

6. **スプー**フ **ィング** : スプーフィング インテリジェンスを有効または無効にするには [編集] をクリックし、Outlook の認証されていない送信者識別情報をオンまたはオフにし、ブロックされるスプーフィングされた送信者からのメッセージに適用するアクションを構成します。 詳細については、フィッ [シング対策ポリシーでのスプーフィング設定に関するトピックを参照してください](set-up-anti-phishing-policies.md#spoof-settings)。

   これらの設定は、EOP のフィッシング対策ポリシーでも使用可能であることに注意してください。

   - **スプーフィング フィルター**の設定: 既定値は **[オン**] です。このままにしておき、お勧めします。 オンにするには、トグルをオフに切り替 **えます**。 詳細については、「EOP でス [プーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング対策保護を無効にする必要がありです。コネクタの拡張フィルター処理を有効にします。 手順については [、「Exchange Online のコネクタ用の拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **[認証されていない送信者] 機能を有効**にします。既定値は **On です**。 オンにするには、トグルをオフに切り替 **えます**。

   - **アクション**: スプーフィング インテリジェンスに失敗したメッセージに対して実行するアクションを指定します。

     **メールが、ドメインのスプーフィングを許可されていないユーザーから送信された場合**:

     - **受信者の迷惑メール フォルダーにメッセージを移動する**
     - **メッセージを検疫する**

   - **設定を確認**します。個々の手順をクリックする代わりに、設定が概要に表示されます。

     - 各セクションで **[編集** ] をクリックすると、関連するページに戻ります。
     - 次の設定は、このページ **で直接 [オン** ] **または [オフ** ] に切り替えることができます。

       - **スプーフィング対策保護を有効にする**
       - **認証されていない送信者機能を有効にする**

   完了したら、[任意のページで保存 **]** をクリックします。

7. **詳細設定**: [ **編集] をクリック** して、高度なフィッシングしきい値を構成します。 詳細については [、ATP フィッシング対策ポリシーの高度なフィッシングしきい値を参照してください](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)。

   - **高度なフィッシングしきい値**: 次のいずれかの値を選択します。

   - **1 - 標準** (これが既定値です)。
   - **2 - Aggressive**
   - **3 - よりすか**
   - **4 - 最ももさもする**

   - **設定を確認します**。[ **編集]** をクリックして、[詳細フィッ **シングのしきい値] ページに戻** ります。

   完了したら、[ページの [保存 **]** をクリックします。

8. [ポリシーの編集 **] \<Name\> ページに戻り**、設定を確認してから [閉じる] を**クリックします**。

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>セキュリティ/コンプライアンス センター&、既定の ATP フィッシング対策ポリシーを変更する

既定の ATP フィッシング対策ポリシーの名前は Office365 AntiPhish Default で、ポリシーの一覧には表示されません。 既定の ATP フィッシング対策ポリシーを変更するには、次の手順を実行します。

1. コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。

2. [フ **ィッシング対策] ページで、[既定** のポリシー] を **クリックします**。

3. ポリシー **の編集に Office365 AntiPhish の [Default]** ページが表示されます。 次のセクションを利用できます。このセクションには、カスタム ポリシーを変更するときに関する同じ [設定が含まれます](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)。

   - **偽装**
   - **スプーフィング**
   - **詳細設定**

   以下の設定は、既定のポリシーを変更する場合には使用できません。

   - ポリシー設定の**セクションと値**は表示されますが、[編集] リンク**Edit**がないため、設定 (ポリシー名、説明、ポリシーの対象者) は変更できません (ポリシー名、説明、ポリシーの対象者) は変更できません。
   - 既定のポリシーは削除できません。
   - 既定のポリシーの優先度は変更できません (常に最後に適用されます)。

4. [ポリシー **の編集] ページで、Office365 AntiPhish Default** ページで設定を確認してから [閉じる] を **クリックします**。

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>カスタム ATP フィッシング対策ポリシーを有効または無効にする

1. コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。

2. 状態列の値に **注意** してください。

   - ポリシーを無効にするには、 **トグ** ルをオフに切り替えます。

   - ポリシーを有効にするには、ト **グルをオン** に切り替えします。

既定のフィッシング対策ポリシーを無効にすることはできません。

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>カスタムの ATP フィッシング対策ポリシーの優先度を設定する

既定では、ATP フィッシング対策ポリシーには、ポリシーの作成順序に基づく優先度が設定されます (新しいポリシーの優先度は、古いポリシーよりも低くなります)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

カスタム ATP フィッシング対策ポリシーは、処理された順に表示されます (最初のポリシーの **優先度** が 0 に設定されている)。 Office365 AntiPhish Default という名前の既定のフィッシング対策ポリシーには、カスタム優先度 **の値 Lowest**が設定されているため、変更できません。

 **注**: コンプライアンス センターでは&、ATP フィッシング対策ポリシーの優先度は、そのポリシーの作成後にのみ変更できます。 PowerShell では、フィッシング対策ルールの作成時に既定の優先度を上書きできます (これは、既存のルールの優先度に影響を与え可能性があります)。

ポリシーの優先度を変更するには、ポリシー **のプロパティの優先度を上** 昇する、または **低** 下します (セキュリティ &/コンプライアンス センターの **優先度** 番号を直接変更することはできません)。 複数のポリシーがある場合のみ、ポリシーの優先度を変更するのは意味があります。

1. コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。

2. 変更するポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. [**ポリシーの編集 \<name\> ]** ポップアップが表示されます。

   - **優先度**値 0 のカスタム ATP フィッシング対策ポリシーでは、優先度の値**を 0**とするだけ**を表示**しています。

   - 優先度の値が最も低いカスタム ATP フィッ**Priority**シング ポリシー (**たとえば、3)** には、[優先度の増**分] ボタンのみが**用意されています。

   - 3 つ以上のカスタムのフィッシング対策ポリシーがある場合、優先度の高い値と最も低い値の間のポリシーでは **、優先度** の高い値と低い優先度 **ボタンの両方が** 使用できます。

4. 優先度 **の値を上** 昇 **または下がり、** 優先度の値 **を変更** します。

5. 完了したら、**[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>セキュリティ センター/コンプライアンス &使用して、ATP フィッシング対策ポリシーを表示する

1. セキュリティ コンプライアンス センター&で、脅威**Threat management**管理 \> **ポリシー** \> **の ATP フィッシング対策に移動します**。

2. 次のいずれかの手順を実行します。

   - 表示するカスタム ATP フィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

   - [ **既定のポリシー]** をクリックして既定のフィッシング対策ポリシーを表示します。

3. [**ポリシーの編集 \<name\> ]** ポップアップが表示され、設定や値を確認できます。

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>セキュリティ/コンプライアンス センター&使用して、ATP フィッシング対策ポリシーを削除する

1. コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。

2. 削除するポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. 表示される**ポリシー ポ \<name\> ップ**アップの [削除] で、[**削除] ポリシーをクリック**し、表示される警告ダイアログ ボックスで [**は**い] をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Exchange Online PowerShell を使用して ATP フィッシング対策ポリシーを構成する

前述のように、ATP のスパム対策ポリシーは、フィッシング対策ポリシーとフィッシング対策ルールで構成されています。

Exchange Online PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの違いは明らかです。 ** \* -AntiPhishPolicy**コマンドレットを使用してフィッシング対策ポリシーを管理し** \* 、-AntiPhishRule**コマンドレットを使用してフィッシング対策ルールを管理します。

- PowerShell では、最初にフィッシング対策ポリシーを作成し、次に、そのルールを適用するポリシーを特定するフィッシング対策ルールを作成します。
- PowerShell では、フィッシング対策ポリシーとフィッシング対策ルールの設定は個別に変更します。
- PowerShell からフィッシング対策ポリシーを削除すると、対応するフィッシング対策ルールは自動で削除されず、逆も同じ手順で削除されます。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell では、フィッシング対策ポリシーの作成は 2 つの手順で行います。

1. フィッシング対策ポリシーを作成します。
2. ルールを適用するフィッシング対策ポリシーを指定するフィッシング対策ルールを作成します。

 **注**:

- 新しいフィッシング対策ルールを作成し、関連付けられていない既存のフィッシング対策ポリシーをそのルールに割り当てて、新しいフィッシング対策ルールを作成することができます。 フィッシング対策ルールを複数のフィッシング対策ポリシーと関連付けすることはできません。

- PowerShell の新しいフィッシング対策ポリシーに以下の設定を構成できます。これらの設定は、ポリシーを作成した後でなけない場合はセキュリティ & コンプライアンス センターでは使用できません。

  - 無効化された新しいポリシーを作成_します_ `$false` **(New-AntiPhishRule コマンドレットで有効** )。
  - _Priority_ _\<Number\>_ **New-AntiPhishRule**コマンドレット上で作成中にポリシーの優先度を設定します (優先順位)。

- PowerShell で作成する新しいフィッシング対策ポリシーは、ポリシーをフィッシング対策規則に割り当てるまで、セキュリティ & コンプライアンス センターには表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシング対策ポリシーを作成する

フィッシング対策ポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次の設定で Research Quarantine という名前のフィッシング対策ポリシーを作成します。

- ポリシーは有効になっています _(Enabled_ パラメーターを使用していません。既定値は次の値です `$true` )。
- 説明は次のとおりです。
- すべての承認済みドメイン、および組織のドメインのターゲット ドメインに対する組織ドメインfabrikam.com。
- 偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。
- メールボックスのインテリジェンスを有効にします。
- メールボックスのインテリジェンス保護を有効にし、検疫アクションを指定します。
- 安全性のヒントを有効にします。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

構文およびパラメーターの詳細については [、New-AntiPhishPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>手順 2: PowerShell を使用してフィッシング対策ルールを作成する

フィッシング対策ルールを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の条件の、Research Department という名前のフィッシング対策ルールを作成します。

- ルールは、Research Quarantine という名前のフィッシング対策ポリシーに関連付けられていです。
- ルールは Research Department という名前のグループのメンバーに適用されます。
- Priority パラメーターを使用しない _ので_ 、既定の優先順位が使用されます。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

構文およびパラメーターの詳細については [、New-AntiPhishRule を参照してください](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを表示する

既存のフィッシング対策ポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと共にすべてのフィッシング対策ポリシーの要約リストを返します。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

この例では、Executives という名前のフィッシング対策ポリシーのすべてのプロパティの値を返します。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

構文およびパラメーターの詳細については [、「Get-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを表示する

既存のフィッシング対策ルールを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、すべてのフィッシング対策ルールと指定したプロパティの要約リストを返します。

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

この例では、Contoso Executives という名前のフィッシング対策ルールのすべてのプロパティの値を返します。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

構文およびパラメーターの詳細については [、「Get-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを変更する

以下の項目以外では、PowerShell でフィッシング対策ポリシーを変更するときにも、このトピックの前述の手順 [1 で説明](#step-1-use-powershell-to-create-an-anti-phish-policy) したように、ポリシーを作成する場合と同じ設定を使用できます。

- 指定 _したポリシー_ を既定のポリシー (すべてのユーザーに適用し、常に優先度が最も低 **く、削除** できない) に切り替える MakeDefault スイッチは、PowerShell でフィッシング対策ポリシーを変更する場合にのみ使用できます。

- フィッシング対策ポリシーの名前は、変更できません **(Set-AntiPhishPolicy コマンドレット** には _Name_ パラメーターはありません)。 セキュリティ/& コンプライアンス センターでフィッシング対策ポリシーの名前を変更する場合、フィッシング対策ルールの名前のみを変更 _しています_。

フィッシング対策ポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-AntiPhishPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを変更する

PowerShell でフィッシング対策ルールを変更するときに使用できない設定は _、無効なルール_ の作成を可能にする Enabled パラメーターのみです。 既存のフィッシング対策ルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合、PowerShell でフィッシング対策ルールを変更するときに利用可能な追加の設定はありません。 手順 [2: PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) を使用して前述の手順で説明したルールを作成するときに同じ設定を使用できます。

フィッシング対策ルールを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については [、「Set-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを有効化または無効化する

PowerShell でフィッシング対策ルールを有効化または無効化すると、フィッシング対策ポリシー全体 (フィッシング対策ルールおよび割り当てられたフィッシング対策ポリシー) が有効または無効になります。 既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。

PowerShell でフィッシング対策ルールを有効化または無効化するには、次の構文を使用します。

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

構文およびパラメーターの詳細については [、「Enable-AntiPhishRule および](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) [Disable-AntiPhishRule」を参照してください](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。

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

- 新しく作成したルールの優先度を設定するには **、New-AntiPhishRule**コマンドレットの_Priority_パラメーターを使用します。

- 既定のフィッシング対策ポリシーには対応するフィッシング対策ルールがありません。また、常に、変更不可能な優先順位の **値 Lowest が設定されます**。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell を使用してフィッシング対策ポリシーを削除する

PowerShell を使用してフィッシング対策ポリシーを削除した場合、対応するフィッシング対策ルールは削除されません。

PowerShell でフィッシング対策ポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ポリシーを削除します。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、Remove-AntiPhishPolicy を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell を使用してフィッシング対策ルールを削除する

PowerShell を使用してフィッシング対策ルールを削除した場合、対応するフィッシング対策ポリシーは削除されません。

PowerShell でフィッシング対策ルールを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシング対策ルールを削除します。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については [、Remove-AntiPhishRule を参照してください](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

ATP フィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。

- コンプライアンス センターから&で、 **脅威管理** \> **ポリシー** \> **の ATP フィッシング対策に移動します**。 ポリシーの一覧とその Status 値 **および Priority** 値 **を確認** します。 詳細を表示するには、次の手順のいずれかを実行します。

  - 一覧からポリシーを選択して、ポップアップに詳細を表示します。
  - [ **既定] ポリシーを** クリックし、ポップアップに詳細を表示します。

- Exchange Online PowerShell でポリシーまたは \<Name\> ルールの名前を置き換え、次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
