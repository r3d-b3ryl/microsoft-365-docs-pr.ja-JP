---
title: ATP フィッシング対策ポリシーを構成する
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
description: 管理者は、Office 365 Advanced Threat Protection (Office 365 ATP) を使用して組織で使用できる高度なフィッシング対策ポリシーを作成、変更、および削除する方法を学習できます。
ms.openlocfilehash: d6655089556f7268222dc47e2196f8aa1fc3da4e
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769222"
---
# <a name="configure-atp-anti-phishing-policies"></a>ATP フィッシング対策ポリシーを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP のフィッシング対策ポリシーは、 [Office 365 Advanced Threat Protection](office-365-atp.md)の一部です。 ATP のフィッシング対策ポリシーは、悪意のある偽造ベースのフィッシング攻撃やその他の種類のフィッシング攻撃から組織を保護するのに役立ちます。 Exchange Online Protection (EOP) と ATP のフィッシング対策ポリシーにおけるフィッシング対策ポリシーの相違点の詳細については、「 [フィッシング対策保護](anti-phishing-protection.md)」を参照してください。

管理者は、既定の ATP のフィッシング対策ポリシーを表示、編集、および構成できます (削除することはできません)。 さらに細分性を高めるために、組織内の特定のユーザー、グループ、またはドメインに適用するカスタムの ATP のフィッシング対策ポリシーを作成することもできます。 カスタム ポリシーは既定のポリシーより常に優先されますが、カスタム ポリシーの優先度 (実行順序) を変更できます。

セキュリティ & コンプライアンスセンターまたは Exchange Online PowerShell で、ATP のフィッシング対策ポリシーを構成できます。

Exchange Online Protection 組織 (つまり、Office 365 ATP を使用しない Microsoft 365 組織) で使用可能なフィッシング対策ポリシーの構成の詳細については、「 [CONFIGURE EOP」の「Configure フィッシング対策ポリシー](configure-anti-phishing-policies-eop.md)」を参照してください。

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>セキュリティ & コンプライアンスセンター vs PowerShell の ATP のフィッシング対策ポリシー

ATP のフィッシング対策ポリシーの基本的な要素は次のとおりです。

- **フィッシングポリシー** : 有効または無効にするフィッシング対策、およびオプションを適用するアクションを指定します。
- **フィッシングルールで** は、フィッシングポリシーの優先順位と受信者フィルター (ポリシーが適用されるユーザー) を指定します。

セキュリティ & コンプライアンスセンターで ATP のフィッシング対策ポリシーを管理する場合、次の2つの要素の違いは明白ではありません。

- ポリシーを作成する場合、実際には、フィッシングルールと関連付けられているフィッシングポリシーを両方に同じ名前を使用して同時に作成しています。
- ポリシーを変更する場合、name、priority、enabled または disabled、および recipient フィルターに関連する設定によって、フィッシングルールが変更されます。 他のすべての設定は、関連付けられたフィッシングポリシーを変更します。
- ポリシーを削除すると、フィッシングルールとそれに関連付けられているフィッシングポリシーが削除されます。

Exchange Online の PowerShell では、ポリシーとルールを個別に管理します。 詳細については、このトピックで後述 [する「Exchange Online の PowerShell を使用して ATP のフィッシング対策ポリシーを構成する](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) 」セクションを参照してください。

すべての Office 365 ATP 組織には、以下のプロパティを持つ Office365 フィッシング対策 Default という組み込みの ATP のフィッシング対策ポリシーがあります。

- ポリシーに関連付けられているフィッシングルール (受信者フィルター) がない場合でも、ポリシーは組織内のすべての受信者に適用されます。
- ポリシーにはカスタムの優先順位の値 **Lowest** が設定されており、変更することはできません (このポリシーは常に最後に適用されます)。 作成するどのカスタム ポリシーも、より高い優先順位を持ちます。
- ポリシーは既定のポリシー ( **IsDefault** のプロパティが `True` の値になっている) であり、既定のポリシーを削除することはできません。

フィッシング対策保護の有効性を高めるために、特定のユーザーまたはユーザーグループに適用される厳密な設定を使用して、カスタムの ATP のフィッシング対策ポリシーを作成することができます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **ATP のフィッシング対策** ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事に記載されている手順を実行するには、事前にアクセス許可を割り当てる必要があります。

  - ATP のフィッシング対策ポリシーを追加、変更、および削除するには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。
    - **組織の管理** または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **検疫管理** 。

  - ATP のフィッシング対策ポリシーへの読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ閲覧者** 。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **表示限定の組織管理** 。

- ATP のフィッシング対策ポリシーの推奨設定については、「 [atp のフィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings)」を参照してください。

- 新規または更新されたポリシーが適用されるまで最大30分かかります。

- フィルタリングパイプラインにフィッシング対策ポリシーを適用する方法については、「 [メール保護の順序と優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを作成する

セキュリティ & コンプライアンスセンターでカスタムの ATP のフィッシング対策ポリシーを作成すると、フィッシングルールと関連付けられているフィッシングポリシーが両方に同じ名前で同時に作成されます。

ATP のフィッシング対策ポリシーを作成する場合、ポリシー名、説明、およびポリシーの適用先を識別する受信者フィルターのみを指定できます。 ポリシーを作成したら、ポリシーを変更して既定のフィッシング対策設定を変更または確認することができます。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。

2. [ **フィッシング対策** ] ページで、[ **作成** ] をクリックします。

3. [ **新しいフィッシング対策ポリシーの作成** ] ウィザードが開きます。 [ **ポリシーに名前** をつける] ページで、次の設定を構成します。

   - **[名前]** : わかりやすい一意のポリシー名を入力します。

   - **[説明]** : ポリシーについての説明を入力します (オプション)。

   完了したら、 **[次へ]** をクリックします。

4. 表示される [ **適用先** ] ページで、ポリシーが適用される内部の受信者を特定します。

   各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、 _\<recipient1\>_ または _\<recipient2\>_ ) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、 _\<recipient1\>_ かつ _\<member of group 1\>_ ) が適用されます。

   [ **条件の追加] を** クリックします。 表示されるドロップダウンで、[適用済みの **場合** ] の条件を選択します。

   - **受信者は** 次のとおりです。組織内で1つ以上のメールボックス、メールユーザー、またはメール連絡先を指定します。
   - **受信者が次のメンバーの** 場合: 組織内の1つまたは複数のグループを指定します。
   - **受信者のドメイン** : 構成された1つ以上の承認済みドメインの受信者を組織に指定します。

   条件を選択すると、対応するドロップ **ダウンボックスが** 表示されます。

   - ボックス内をクリックし、値の一覧をスクロールして選択します。
   - ボックス内をクリックして入力を開始し、リストにフィルターを適用して値を選択します。
   - その他の値を追加するには、ボックスの空の領域をクリックします。
   - 個々のエントリを削除するには、その値の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。
   - 条件全体を削除するには、条件の [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。

   別の条件を追加するには、[ **条件の追加** ] をクリックし、[ **適用** 時] で残りの値を選択します。

   例外を追加するには、[ **条件の追加** ] をクリックし、 **Except if** で例外を選択します。 設定と動作は、条件とまったく同じです。

   完了したら、 **[次へ]** をクリックします。

5. 表示される [ **設定の確認** ] ページで、設定を確認します。 各設定で [ **編集** ] をクリックして、変更を行うことができます。

   完了したら、[ **このポリシーの作成** ] をクリックします。

6. 表示される確認ダイアログで [ **OK** ] をクリックします。

これらの一般的なポリシー設定を使用して ATP のフィッシング対策ポリシーを作成した後、次のセクションの手順を使用して、ポリシーの保護設定を構成します。

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>セキュリティ & コンプライアンスセンターを使用して ATP のフィッシング対策ポリシーを変更する

ATP のフィッシング対策ポリシーを変更するには、次の手順を使用します。これは、作成した新しいポリシー、または既にカスタマイズした既存のポリシーです。

1. まだ存在しない場合は、セキュリティ & コンプライアンスセンターを開き、[ **脅威管理** \> **ポリシー** ] \> **ATP のフィッシング対策** に移動します。

2. 変更するカスタムの ATP のフィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. [ **ポリシー \<name\> の編集** のポップアップを表示します。 いずれかのセクションで [ **編集** ] をクリックすると、そのセクションの設定にアクセスできます。

   - 次の手順は、セクションが表示される順序で示されていますが、連続していません (任意の順序でセクションを選択して変更することができます)。

   - セクションで [ **編集** ] をクリックすると、使用可能な設定がウィザード形式で表示されますが、ページ内を任意の順序で移動できます。または、[すべての **Close** ページに **保存** **] を** クリックして ![ 、[ ](../../media/scc-remove-icon.png) **ポリシー \<name\> の編集** ] ページに戻ることができます。

4. **ポリシー設定** : [ **編集** ] をクリックして、前のセクションで [ポリシーを作成](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) したときに使用したものと同じ設定を変更します。

   - **[名前]**
   - **説明**
   - **適用先**
   - **設定を確認する**

   完了したら、[任意のページに **保存** ] をクリックします。

5. **偽装** : [ **編集** ] をクリックして、ポリシー内の保護された送信者と保護されたドメインを変更します。 これらの設定は、受信メッセージの From アドレスで (個別またはドメインによって) 検索するスプーフィングされた送信者を識別するポリシーの条件です。 詳細については、「 [ATP のフィッシング対策ポリシー」の「偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)」を参照してください。

   - **保護するユーザーを追加する** : 既定値は **Off** です。 これをオンにするには、トグルを **[オン** ] にして、表示される [ **ユーザーの追加** ] ボタンをクリックします。

     [ **ユーザーの追加** ] ポップアップが表示されたら、次の値を構成します。

     - **メールアドレス** :

        - ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。
        - ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。
        - エントリを削除するには、ユーザーの [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。

     - **Name** : この値は、選択したメールアドレスに基づいて設定されますが、変更することができます。

     完了したら、[任意のページに **保存** ] をクリックします。

     既存のエントリを編集するには、一覧で保護されたユーザーを選択します。

     > [!NOTE]
     > セキュリティ & コンプライアンスセンターまたは PowerShell には、最大で60ユーザーを入力できます。
       
   - **保護するドメインを追加する** : 次の設定の1つまたは両方を構成します。

     - **自分が所有するドメインを自動的に追加** する: 既定値は **Off** です。 これをオンにするには、トグルを **[オン** ] にします。
     - **カスタムドメインを含める** : 既定値は **Off** です。 これをオンにするには、トグルを **[オン** ] にして、[ **ドメインの追加** ] ボックスにドメイン名 (contoso.com など) を入力し、enter キーを押して、必要に応じて繰り返します。

     > [!NOTE]
     > セキュリティ & コンプライアンスセンターまたは PowerShell には、最大で50のドメインを入力できます。

   - **アクション** : [ **編集** ] をクリックします。

     - **偽装ユーザーによって電子メールが送信** される場合: スプーフィングされた送信者が、[ **保護するユーザーの追加** ] で指定した保護されたユーザーのいずれかであるメッセージに対して、次のいずれかのアクションを構成します。

       - **どの操作も適用しない**
       - **他の電子メールアドレスへのメッセージのリダイレクト**
       - **迷惑メールフォルダーにメッセージを移動する**
       - **メッセージを検疫する**
       - **メッセージを配信し、その他のアドレスを Bcc 行に追加する**
       - **配信前にメッセージを削除する**

     - **偽装ドメインによって電子メールが送信** される場合: スプーフィングされた送信者が、 **保護するドメインの追加** で指定した保護されたドメインのいずれかにあるメッセージに対して、次のいずれかのアクションを構成します。

     - **どの操作も適用しない**
     - **他の電子メールアドレスへのメッセージのリダイレクト**
     - **迷惑メールフォルダーにメッセージを移動する**
     - **メッセージを検疫する**
     - **メッセージを配信し、その他のアドレスを Bcc 行に追加する**
     - **配信前にメッセージを削除する**

   - [ **偽装の安全性のヒントを有効にする** ] をクリックし、次のいずれかの設定を構成します。

     - **偽装ユーザーのヒントを表示する** : 既定値は **Off** です。 これをオンにするには、トグルを **[オン** ] にします。
     - **偽装ドメインのヒントを表示する** : 既定値は **Off** です。 これをオンにするには、トグルを **[オン** ] にします。
     - **通常の文字にヒントを表示** する: 既定値は **Off** です。 これをオンにするには、トグルを **[オン** ] にします。

     完了したら、 **[保存]** をクリックします。

   - **メールボックスインテリジェンス** :

     - **メールボックスインテリジェンスを有効に** しますか。既定値は **[オン** ] です。 この機能をオフにするには、トグルを [ **オフ** ] にします。

     - **[****メールボックスインテリジェンスベースの偽装保護を有効にする]** : この設定は、 **メールボックスインテリジェンスを有効にする** 場合にのみ使用できます。

       で **偽装ユーザーによって電子メールが送信** された場合は、メールボックスインテリジェンスに失敗したメッセージに対して次のいずれかの操作を行うことができます (保護されたユーザーと保護されたドメインに対して使用可能なものと同じもの)。

       - **どの操作も適用しない**
       - **他の電子メールアドレスへのメッセージのリダイレクト**
       - **迷惑メールフォルダーにメッセージを移動する**
       - **メッセージを検疫する**
       - **メッセージを配信し、その他のアドレスを Bcc 行に追加する**
       - **配信前にメッセージを削除する**

   - **信頼できる差出人とドメインを追加** する: ポリシーの例外を指定します。

     - **信頼できる送信者** :

       - ボックス内をクリックし、ユーザーの一覧をスクロールして選択します。
       - ボックス内をクリックして入力を開始し、リストにフィルターを適用してユーザーを選択します。
       - エントリを削除するには、ユーザーの [削除] アイコン **をクリックし** ![ ](../../media/scc-remove-icon.png) ます。

     - [ **信頼されたドメイン** ]: ドメイン名 (たとえば、contoso.com) を入力し、enter キーを押して、必要に応じて繰り返します。

   - **設定を確認** します。個々の手順をクリックする代わりに、設定が概要で表示されます。

     - 各セクションで [ **編集** ] をクリックすると、関連するページに戻ることができます。
     - このページでは、次の設定の **オン** と **オフ** を直接切り替えることができます。

       - **保護されたユーザー**
       - **保護されたドメイン** \>**所有** しているドメインを含める
       - **保護されたドメイン** \>**保護されたドメイン** (カスタムドメイン)
       - **メールボックス インテリジェンス**

   完了したら、[任意のページに **保存** ] をクリックします。

6. **スプーフィング** : [ **編集** ] をクリックして、スプーフィングインテリジェンスを有効または無効にしたり、Outlook で認証されていない送信者の識別をオンまたはオフにしたり、ブロックされたスプーフィングされた送信者からのメッセージに適用するアクションを構成します。 詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。

   なお、これらの設定は EOP のフィッシング対策ポリシーでも使用できます。

   - **フィルター設定のスプーフィング** : 既定値は **on** で、そのままにすることをお勧めします。 この機能をオフにするには、トグルを [ **オフ** ] にします。 詳細については、「 [Configure スプーフ知能 IN EOP」](learn-about-spoof-intelligence.md)を参照してください。

     > [!NOTE]
     > MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング防止保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。 手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

   - [認証されていない **送信者の機能を有効にする** ]: 既定値は **[オン** ] です。 この機能をオフにするには、トグルを [ **オフ** ] にします。

   - **アクション** : スプーフィングインテリジェンスに失敗したメッセージに対して実行するアクションを指定します。

     **ドメインのスプーフィングが許可されていないユーザーによって電子メールが送信** される場合:

     - **受信者の迷惑メールフォルダーにメッセージを移動する**
     - **メッセージを検疫する**

   - **設定を確認** します。個々の手順をクリックする代わりに、設定が概要で表示されます。

     - 各セクションで [ **編集** ] をクリックすると、関連するページに戻ることができます。
     - このページでは、次の設定の **オン** と **オフ** を直接切り替えることができます。

       - **スプーフィング対策保護を有効にする**
       - **認証されていない送信者機能を有効にする**

   完了したら、[任意のページに **保存** ] をクリックします。

7. **詳細設定** : [ **編集** ] をクリックして、詳細なフィッシングしきい値を構成します。 詳細については、「 [ATP のフィッシング対策ポリシー」の「Advanced フィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)」を参照してください。

   - **[Advanced フィッシングしきい** 値]: 次のいずれかの値を選択します。

   - **1-標準** (これは既定値です)
   - **2-アグレッシブ**
   - **3つ以上のアグレッシブ**
   - **4-最も積極的**

   - **設定を確認** します。 [ **編集** ] をクリックすると、[ **詳細なフィッシングのしきい値** ] ページに戻ることができます。

   完了したら、[どちらかのページで **保存** ] をクリックします。

8. [ **ポリシー \<Name\> の編集** ] ページに戻り、設定を確認してから、[ **閉じる** ] をクリックします。

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>セキュリティ & コンプライアンスセンターを使用して既定の ATP のフィッシング対策ポリシーを変更する

既定の ATP のフィッシング対策ポリシーの名前は、Office365 フィッシング対策 Default で、ポリシーの一覧には表示されません。 既定の ATP のフィッシング対策ポリシーを変更するには、次の手順を実行します。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。

2. [ **フィッシング対策** ] ページで、[ **既定のポリシー** ] をクリックします。

3. [ **ポリシーの Office 365 フィッシング対策の既定の編集** ] ページが表示されます。 次のセクションを使用できます。これには、 [カスタムポリシーを変更](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)するときに、同一の設定が含まれています。

   - **偽装**
   - **なりすます**
   - **詳細設定**

   次の設定は、既定のポリシーを変更するときには使用できません。

   - **ポリシー設定** のセクションと値は表示できますが、 **編集** リンクはありません。そのため、設定 (ポリシー名、説明、ポリシーの適用先 (すべての受信者に適用)) を変更することはできません。
   - 既定のポリシーを削除することはできません。
   - 既定のポリシーの優先度を変更することはできません (常に最後に適用されます)。

4. [ **Policy The Office365 フィッシング対策 Default** ] ページで、設定を確認し、[ **閉じる** ] をクリックします。

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>カスタム ATP フィッシング対策ポリシーを有効または無効にする

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。

2. [ **状態** ] 列の値に注目してください。

   - トグルを [ **オフ** ] にして、ポリシーを無効にします。

   - トグルに切り替えて、 **ポリシーを有効** にします。

既定のフィッシング対策ポリシーを無効にすることはできません。

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>カスタム ATP フィッシング対策ポリシーの優先度を設定する

既定では、ATP のフィッシング対策ポリシーには、作成された順序に基づく優先度が与えられます (新しいポリシーは、以前のポリシーよりも優先度が低いです)。 優先度番号が小さいほど、ポリシーの優先度が高くなる (0 が最優先) ことを意味し、ポリシーは優先順位に従って処理されます (優先度の高いポリシーは、優先度の低いポリシーよりも先に処理されます)。 2つのポリシーが同じ優先順位を持つことはできません。最初のポリシーが適用されると、ポリシーの処理は停止します。

優先順位と複数のポリシーを評価し適用する方法の詳細については、「[メール保護の優先順位](how-policies-and-protections-are-combined.md)」を参照してください。

カスタム ATP のフィッシング対策ポリシーは、処理順に表示されます (最初のポリシーの **優先度** 値は0になります)。 Office365 フィッシング対策 Default という既定のフィッシング対策ポリシーは、カスタムの優先度の値を **最小** にし、それを変更することはできません。

 **注** : セキュリティ & コンプライアンスセンターでは、作成後に ATP のフィッシング対策ポリシーの優先度のみを変更できます。 PowerShell では、フィッシングルールを作成するときに既定の優先順位を上書きできます (既存のルールの優先度に影響する場合があります)。

ポリシーの優先度を変更するには、ポリシーのプロパティで [ **優先度を上げる** ] または [ **優先度を下げる** ] をクリックします (セキュリティ & コンプライアンスセンターで **優先度** を直接変更することはできません)。 ポリシーの優先度を変更することは、複数のポリシーがある場合にのみ有効になります。

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。

2. 変更するポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. [ **ポリシー \<name\> の編集** のポップアップを表示します。

   - **優先順位** の値が **0** のカスタム ATP のフィッシング対策ポリシーでは、[ **優先度を下げる** ] ボタンのみを使用できます。

   - **優先度** の低い値 (たとえば **3** ) を持つカスタム ATP のフィッシング対策ポリシーには、[ **優先度を上げる** ] ボタンだけが使用できます。

   - 3つ以上のカスタムのマルウェア対策ポリシーを所有している場合、最高の優先度と最も低い優先度の値の間のポリシーでは、[優先度を **上げる** ] ボタンと [ **優先度を下げる** ] ボタンの両方を使用できます。

4. [優先 **度を上げる** ] または [ **優先度を下げる** ] をクリックし、 **優先度** の値を変更します。

5. 完了したら、 **[閉じる]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを表示する

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。

2. 次のいずれかの手順を実行します。

   - 表示するカスタムの ATP のフィッシング対策ポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

   - [ **既定のポリシー** ] をクリックして、既定のフィッシング対策ポリシーを表示します。

3. [ **ポリシー \<name\> の編集** ] ポップアップが表示され、設定と値を表示できます。

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>セキュリティ & コンプライアンスセンターを使用して、ATP のフィッシング対策ポリシーを削除する

1. セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。

2. 削除するポリシーを選択します。 既に選択されている場合は、選択を解除してもう一度選択します。

3. 表示される [ **ポリシー \<name\> の編集** ] ポップアップで、[ **ポリシーの削除** ] をクリックし、表示される警告ダイアログボックスで [ **はい** ] をクリックします。

既定のポリシーは削除できません。

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Exchange Online PowerShell を使用して ATP のフィッシング対策ポリシーを構成する

前述したように、ATP のスパム対策ポリシーは、フィッシングポリシーとフィッシングルールで構成されています。

Exchange Online PowerShell では、フィッシングポリシーとフィッシングルールの違いが明らかです。 フィッシングポリシーを管理するには、 **\* -get-antiphishpolicy** コマンドレットを使用して、 **\* -new-antiphishrule** コマンドレットを使用してフィッシングルールを管理します。

- PowerShell では、フィッシングポリシーを最初に作成してから、ルールが適用されるポリシーを識別するフィッシングルールを作成します。
- PowerShell では、フィッシングポリシーおよびフィッシングルールの設定を個別に変更します。
- PowerShell からフィッシングポリシーを削除すると、対応するフィッシングルールは自動的に削除されず、その逆も同様です。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell を使用してフィッシング対策ポリシーを作成する

PowerShell でのフィッシング対策ポリシーの作成は、次の2つの手順からなるプロセスです。

1. フィッシングポリシーを作成します。
2. ルールが適用されるフィッシングポリシーを指定するフィッシングルールを作成します。

 **注** :

- 新しいフィッシングルールを作成し、関連付けられていない既存のアンチフィッシングポリシーをそのルールに割り当てることができます。 フィッシングルールは、複数のフィッシングポリシーに関連付けることはできません。

- 次の設定は、ポリシーを作成するまではセキュリティ & コンプライアンスセンターでは使用できない PowerShell の新しいフィッシングポリシーで構成できます。

  - 新しいポリシーを無効として _Enabled_ 作成し `$false` ます ( **new-antiphishrule** コマンドレットでは有効)。
  - New-antiphishrule コマンドレットで、作成中にポリシーの優先度を設定します ( _優先度_ _\<Number\>_ )。 **New-AntiPhishRule**

- PowerShell で作成した新しいフィッシングポリシーは、ポリシーをフィッシングルールに割り当てるまで、セキュリティ & コンプライアンスセンターに表示されません。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>手順 1: PowerShell を使用してフィッシングポリシーを作成する

フィッシングポリシーを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

この例では、次の設定を使用して Research Quarantine という名前のフィッシングポリシーを作成します。

- このポリシーは有効になっています ( _enabled_ パラメーターは使用していません。既定値はです `$true` )。
- 説明は、「研究部門のポリシー」です。
- すべての承認済みドメインに対する組織ドメインの保護と、fabrikam.com の対象となるドメインの保護を有効にします。
- 偽装から保護するユーザーとして Mai Fujito (mfujito@fabrikam.com) を指定します。
- メールボックスのインテリジェンスを有効にします。
- メールボックスインテリジェンス保護を有効にし、検疫アクションを指定します。
- 安全のヒントを有効にします。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)」を参照してください。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>手順 2: PowerShell を使用してフィッシングルールを作成する

フィッシングルールを作成するには、次の構文を使用します。

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

この例では、次の条件を使用して Research Department という名前のフィッシングルールを作成します。

- ルールは、Research Quarantine という名前のフィッシングポリシーに関連付けられています。
- ルールは Research Department という名前のグループのメンバーに適用されます。
- _Priority_ パラメーターを使用していないので、既定の優先度が使用されます。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)」を参照してください。

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell を使用してフィッシングのポリシーを表示する

既存のフィッシングポリシーを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定されたプロパティと共にすべてのフィッシングポリシーの要約リストを返します。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

この例では、"重役" という名前のフィッシングポリシーのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)」を参照してください。

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell を使用してフィッシングのルールを表示する

既存のフィッシングルールを表示するには、次の構文を使用します。

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

この例では、指定したプロパティと共に、フィッシングのすべてのルールの要約リストを返します。

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

この例では、Contoso 重役という名前のフィッシングルールのすべてのプロパティ値を返します。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)」を参照してください。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell を使用してフィッシングポリシーを変更する

このトピックで前述したように、「 [手順 1: powershell を使用してフィッシングポリシーを作成する](#step-1-use-powershell-to-create-an-anti-phish-policy) 」で説明されているように、ポリシーの作成時に powershell のフィッシングポリシーを変更する場合は、次の項目以外にも同じ設定を使用できます。

- 指定されたポリシーを既定のポリシー (すべてのユーザーに適用して、常に **最下位** の優先度を適用し、削除することはできません) に変更する _makedefault_ スイッチは、PowerShell のフィッシングポリシーを変更する場合にのみ使用できます。

- フィッシングポリシーの名前を変更することはできません ( **get-antiphishpolicy** コマンドレットには _Name_ パラメーターがありません)。 セキュリティ & コンプライアンスセンターでフィッシング対策ポリシーの名前を変更する場合、フィッシング _ルール_ の名前のみを変更しています。

フィッシングポリシーを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)」を参照してください。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell を使用してフィッシングルールを変更する

PowerShell でフィッシングルールを変更するときには使用できない唯一の設定は、無効にされたルールを作成できる _有効_ なパラメーターです。 既存のフィッシングルールを有効または無効にするには、次のセクションを参照してください。

それ以外の場合は、PowerShell でフィッシングルールを変更しても、追加の設定は使用できません。 このトピックで前述した「 [手順 2: PowerShell を使用してフィッシングルールを作成する](#step-2-use-powershell-to-create-an-anti-phish-rule) 」で説明されているように、ルールを作成する場合にも同じ設定を使用できます。

フィッシングルールを変更するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)」を参照してください。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell を使用してフィッシングルールを有効または無効にする

PowerShell でフィッシングルールを有効または無効にすると、フィッシング対策ポリシー全体 (フィッシングルールおよび割り当てられたフィッシングポリシー) が有効または無効になります。 既定のフィッシング対策ポリシーを有効または無効にすることはできません (常にすべての受信者に適用されます)。

PowerShell でフィッシングルールを有効または無効にするには、次の構文を使用します。

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

この例では、Marketing Department という名前のフィッシングルールを無効にします。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

この例では、同じルールを有効化します。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) 」および「 [Disable-new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)」を参照してください。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell を使用してフィッシングルールの優先度を設定する

ルールに設定できる優先度の最高値値は 0 です。 設定できる最低値はルールの数に依存します。 たとえば、ルールが五つある場合、使用できる優先度の値は 0 から 4 です。 既存の一つのルールの優先度を変更すると、他のルールにも連鎖的な影響が起こりえます。 たとえば、カスタム ルールが 5 つあって (優先度 0 から 4)、1 つのルールの優先度を 2 に変更した場合には、既存の優先度 2 のルールは優先度 3 に変更され、優先度 3 は優先度 4 に変更されます。

PowerShell でフィッシングルールの優先度を設定するには、次の構文を使用します。

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

この例では、Marketing Department というルールの優先度を 2 に設定しています。優先度が 2 以下のすべての既存のルールは、優先度が 1 ずつ下がります (優先度番号が 1 ずつ増加します)。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注** :

- 新しいルールの作成時に優先度を設定するには、代わりに **new-antiphishrule** コマンドレットで _priority_ パラメーターを使用します。

- 既定のフィッシングポリシーには、対応するフィッシングルールが設定されておらず、常に未設定の優先度の値が **最低** になっています。

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell を使用してフィッシングポリシーを削除する

PowerShell を使用してフィッシングポリシーを削除しても、対応するフィッシングルールは削除されません。

PowerShell でフィッシングポリシーを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシングポリシーを削除します。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)」を参照してください。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell を使用してフィッシングルールを削除する

PowerShell を使用してフィッシングルールを削除しても、対応するフィッシングポリシーは削除されません。

PowerShell でフィッシングルールを削除するには、次の構文を使用します。

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

この例では、Marketing Department という名前のフィッシングルールを削除します。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

構文およびパラメーターの詳細については、「 [new-antiphishrule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)」を参照してください。

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

ATP のフィッシング対策ポリシーが正常に構成されたことを確認するには、次のいずれかの手順を実行します。

- セキュリティ & コンプライアンスセンターで、[ **脅威管理** \> **ポリシー** \> **ATP のフィッシング対策** ] に移動します。 ポリシーの一覧、その **状態** の値、およびその **優先度** の値を確認します。 詳細を表示するには、次のいずれかの手順を実行します。

  - リストからポリシーを選択し、フライアウトの詳細を表示します。
  - [ **既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。

- Exchange Online PowerShell で、を \<Name\> ポリシーまたはルールの名前に置き換えて、次のコマンドを実行し、設定を確認します。

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
