---
title: 送信スパム ポリシーを構成する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 送信電子メールの送信にサービスを使用すると、送信スパムフィルターは常に有効になり、それによって、そのサービスと目的の受信者を使用して組織が保護されます。
ms.openlocfilehash: 43939022dc365f5b28418d96ae1217e159312da1
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808442"
---
# <a name="configure-the-outbound-spam-policy"></a>送信スパム ポリシーを設定する

送信電子メールの送信にサービスを使用すると、送信スパムフィルターは常に有効になり、それによって、そのサービスと目的の受信者を使用して組織が保護されます。 受信フィルターと同様に、送信スパムフィルターは、接続フィルターとコンテンツフィルターで構成され、特定のコントロールで送信メッセージを処理することができます。 送信スパムフィルターポリシー設定の種類:

- 既定値: 既定の送信スパムフィルターポリシーを使用して、企業全体のスパムフィルター設定を構成します。 このポリシーは名前を変更できません。また、常にオンになります。

- カスタム: カスタム送信スパムフィルターポリシーを細分化して、組織内の特定のユーザー、グループ、またはドメインに適用することができます。 カスタム ポリシーは、常に、既定のポリシーより優先されます。 各カスタムポリシーの優先度を変更することによって、カスタムポリシーを実行する順序を変更することができます。ただし、ユーザーが複数のポリシーと一致する場合は、最上位の優先度 (つまり、0に最も近い) ポリシーが適用されます。

> [!NOTE]
> [Office 365 での送信スパム制御](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls)の詳細については、を参照してください。 <br><br> 送信スパムポリシーに対する更新は現在ロールアウトされており、予定されている更新は2019年10月末までに完了しています。 この間、一部のオプションは使用できない場合があります。  詳細については、「 [Office 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?featureid=54125)」を参照してください。 

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

予想所要時間 : 5 分

この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可については、「[Exchange Online の機能アクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)」の「スパム対策」のエントリを参照してください。

以下の手順はリモート PowerShell 経由でも実行することができます。 [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) コマンドレットを使用して設定を確認し、[Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) を使用して送信スパム ポリシー設定を編集します。 Windows PowerShell を使用して Exchange Online Protection に接続する方法については、「[Exchange Online Protection の PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

## <a name="use-the-security-and-compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>セキュリティ/コンプライアンスセンター (SCC) を使用して既定の送信スパムポリシーを編集する

既定の送信スパム ポリシーを編集するには、次の手順を使用します。

### <a name="to-configure-the-default-outbound-spam-policy"></a>既定の送信スパム ポリシーを構成する方法

1. SCC で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。

2. [**送信スパムフィルターポリシー (ALWAYS ON)** ] セクションを展開し、[**ポリシーの編集**] をクリックします。

3. [**通知**] セクションを展開し、送信メッセージに関する次のチェックボックスをオンにして、[**ユーザーの追加**] を選択して、関連付けられた電子メールアドレスまたはアドレスを付随するダイアログボックスに追加します。 (これらは、有効な SMTP 宛先として解決される場合は、配布リストになります)。

   - **疑わしいすべての送信電子メールメッセージのコピーを次の電子メールアドレスまたはアドレスに送信**します。これらは、フィルターによってスパムとしてマークされたメッセージです (SCL レベルに関係なく)。 フィルターによって拒否されませんが、より危険度の高い配信プールでルーティングされます。 複数のアドレスはセミコロンで区切ります。 指定された受信者はブラインド カーボン コピー (BCC) アドレスとしてメッセージを受け取ることに注意してください (差出人フィールドと宛先フィールドは元の送信者と受信者です)。

   - 送信**者が送信スパムの送信をブロックされている場合は、次の電子メールアドレスに通知を送信**します。複数のアドレスはセミコロンで区切ります。

   特定のユーザーが大量のスパムまたはその他の送信の異常を検出した場合、ユーザーは電子メールメッセージの送信を制限され、指定された電子メールアドレスに通知が送信されます。

   この設定の使用を指定したドメインの管理者は、このユーザーによるメッセージ送信がブロックされていることを通知されます。  この通知がどのように表示されるかを確認するには、「[送信者が送信スパムの送信をブロックされる場合の通知例](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)」をご覧ください。

   > [メモ!]ユーザーが制限されていることを示すシステム警告も生成されます。  警告の詳細、およびユーザーの回復方法については、「[制限付きユーザーポータルからのユーザーの削除](removing-user-from-restricted-users-portal-after-spam.md)」を参照してください。

4. [**受信者の制限**] セクションを展開して、内部および外部の受信者の1時間ごとに、1日あたりの最大数と共に、ユーザーが送信できる受信者の最大数を指定します。

    > [メモ!]入力の最大数は1万です。  詳細については[、「Exchange online 内の受信および送信の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)」を参照してください。

7. ユーザーが指定した制限を超えた場合に実行する**アクション**を指定します。  可能なアクションは次のとおりです。
    * **ユーザーが次の日までメールを送信**できないように制限します。  送信の制限 (内部、外部、または毎日) を超えると、管理者のための通知が生成されます。ユーザーは、UTC 時間に基づいて、次の日まで追加の電子メールを送信することはできません。 管理者がこのブロックを上書きすることはできません。

    * **ユーザーがメールを送信**できないように制限します。  送信の制限 (内部、外部、または毎日) を超えると、管理者に対して通知が生成され、管理者が制限を削除するまで、ユーザーはそれ以上メールを送信できなくなります。  このような場合、ユーザーは [制限された[ユーザー] ページ](removing-user-from-restricted-users-portal-after-spam.md)に一覧表示されます。  リストから削除されると、その日に対してユーザーが再度制限されることはありません。

    * **アクション/アラートのみ**。 送信制限を超えた場合 (内部、外部、または毎日) は、管理者に対して通知が生成されますが、ユーザーを制限するアクションは実行されません。

6. [**適用先**] セクションを展開し、このポリシーを適用するユーザー、グループ、およびドメインを指定する条件ベースのルールを作成します。 それぞれが一意の条件であれば、複数の条件を作成できます。  注: 複数の条件が指定されている場合、ユーザーはすべての条件を満たす必要があります。  

      * ユーザーを選択するに**は**、[送信者] を選択します。 次のダイアログボックスで、ユーザー選択リストから会社の1人または複数の送信者を選択し、[追加] をクリックします。 リスト上にない送信者を追加するには、電子メール アドレスを入力してから [名前の確認] をクリックします。 選択が完了したら、 [OK] をクリックして、メイン画面に戻ります。

      * [グループ] を選択するには、[**送信者がメンバー**である] を選択します。 その後、それに続くダイアログ ボックスでグループを選択または指定します。 [OK] をクリックして、メイン画面に戻ります。

      * [ドメイン] を選択するには、[**送信者ドメイン**] を選択します。 その後、それに続くダイアログ ボックスでドメインを追加します。 [OK] をクリックして、メイン画面に戻ります。

        ルール内で例外を作成できます。 たとえば、特定のドメインを除くすべてのドメインからのメッセージをフィルター処理できます。 [例外の追加] をクリックしてから、他の条件の作成方法と同じように例外条件を作成します。

        送信スパムポリシーのグループへの適用は、メールが有効なセキュリティグループに対してのみサポートされています。

7. **[保存]** をクリックします。

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>特定のユーザーセットのカスタムポリシーを作成するには
1. SCC で、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動します。

2. [**送信ポリシーの作成**] ボタンをクリックします。

3. [**通知**] セクションを展開し、送信メッセージに関する次のチェックボックスをオンにして、[**ユーザーの追加**] を選択して、関連付けられた電子メールアドレスまたはアドレスを付随するダイアログボックスに追加します。

4. [**受信者の制限**] セクションを展開して、ユーザーが送信できる受信者の最大数、内部および外部の受信者の場合は1時間ごと、1日あたりの最大数を指定します。

7. ユーザーが指定した制限を超えた場合に実行する**アクション**を指定します。

6. [**適用先**] セクションを展開し、このポリシーを適用するユーザー、グループ、およびドメインを指定する条件ベースのルールを作成します。 それぞれが一意の条件であれば、複数の条件を作成できます。  

8. [**保存**] をクリックします。

## <a name="for-more-information"></a>詳細情報

[迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[送信メッセージにおける危険度の高い配信プール](high-risk-delivery-pool-for-outbound-messages.md)

[スパム対策保護に関してよく寄せられる質問](anti-spam-protection-faq.md)
