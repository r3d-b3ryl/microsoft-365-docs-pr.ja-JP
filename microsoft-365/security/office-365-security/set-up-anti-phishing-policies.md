---
title: フィッシング対策ポリシー
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
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) と Microsoft Defender for Office 365 で利用できるフィッシング対策ポリシーについて説明します。
ms.openlocfilehash: f1ffebbca2d3a77d1a0c10d14205e52108614043
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908355"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 のフィッシング対策ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


フィッシング対策保護設定を構成するポリシーは、Exchange Online メールボックスを持つ Microsoft 365 組織、Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織、および Office 365 組織用の Microsoft Defender で利用できます。

Office 365 向け Microsoft Defender のフィッシング対策ポリシーは、Defender for Office 365 を使用している組織でのみ利用できます。 以下に例を示します。

- Microsoft 365 Enterprise E5、Microsoft 365 Education A5 など。
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender for Office 365 をアドオンとして追加](https://products.office.com/exchange/advance-threat-protection)

EOP のフィッシング対策ポリシーと microsoft Defender for Office 365 のフィッシング対策ポリシーの大きな違いについて、次の表で説明します。

****

|機能|EOP のフィッシング対策ポリシー|Microsoft Defender for Office 365 のフィッシング対策ポリシー|
|---|:---:|:---:|
|自動的に作成される既定のポリシー|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|カスタム ポリシーを作成する|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|ポリシー設定<sup>\*</sup>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|偽装設定||![チェック マーク](../../media/checkmark.png)|
|スプーフィング設定|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|高度なフィッシングのしきい値||![チェック マーク](../../media/checkmark.png)|
|

<sup>\*</sup> 既定のポリシーでは、ポリシー名と説明は読み取り専用であり (説明は空白です)、ポリシーを適用するユーザーを指定することはできません (既定のポリシーはすべての受信者に適用されます)。

フィッシング対策ポリシーを構成するには、次の記事を参照してください。

- [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)

- [Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)](configure-atp-anti-phishing-policies.md)

この記事の残りの部分では、EOP および Defender for Office 365 のフィッシング対策ポリシーで使用可能な設定について説明します。

## <a name="policy-settings"></a>ポリシー設定

EOP および Microsoft Defender for Office 365 のフィッシング対策ポリシーでは、次のポリシー設定を使用できます。

- **[** 名前]: 既定のフィッシング詐欺対策ポリシーの名前は変更できますが、作成したカスタム ポリシーに名前を付け、名前を変更できます。

- **説明** 既定のフィッシング詐欺対策ポリシーに説明を追加できますが、作成するカスタム ポリシーの説明を追加および変更できます。

- **適用:** フィッシング対策ポリシーが適用される内部受信者を識別します。 この値はカスタム ポリシーでは必須であり、既定のポリシーでは使用できません (既定のポリシーはすべての受信者に適用されます)。

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

  - **受信者:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
  - **受信者は、組織内の** 1 つ以上のグループのメンバーです。
  - **受信者のドメイン** は、Microsoft 365 で構成されている 1 つ以上の承認されたドメインです。

  - **条件**: ルールの例外を除く。 設定と動作は条件とまったく同じになります。

    - **受信者が**
    - **受信者が次のメンバーである**
    - **受信者のドメインが次の場合**

  > [!NOTE]
  > [**適用先**] 設定は、ポリシーが適用されるメッセージ受信者を識別するためのカスタムフィッシング対策ポリシー <u>で必要です</u>。 Office 365 用の Microsoft Defender のフィッシング対策ポリシーには、[](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)この記事で後述するように、偽装保護を受け取る個々の<u></u>送信者の電子メール アドレスまたは送信者ドメインを指定できる偽装設定があります。

## <a name="spoof-settings"></a>スプーフィング設定

スプーフィングとは、電子メール メッセージの From アドレス (メール クライアントに表示される送信者アドレス) が電子メール ソースのドメインと一致しない場合です。 スプーフィングの詳細については [、「Microsoft 365](anti-spoofing-protection.md)のスプーフィング対策保護」を参照してください。

次のスプーフィング設定は、EOP および Microsoft Defender for Office 365 のフィッシング対策ポリシーで使用できます。

- **スプーフィング対策保護**: スプーフィング対策保護を有効または無効にします。 有効のままにすることをお勧めします。 スプーフィング **インテリジェンス ポリシーを使用して、特定** のスプーフィングされた内部および外部の送信者を許可またはブロックします。 詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。

  > [!NOTE]
  >
  > - スプーフィング対策保護は、既定のフィッシング対策ポリシーと、作成した新しいカスタムフィッシング対策ポリシーで既定で有効になっています。
  >
  > - MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング対策保護を無効にする必要があります。コネクタの拡張フィルターを有効にする必要があります。 手順については [、「Exchange Online のコネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。
  >
  > - スプーフィング対策保護を無効にすると、複合認証チェックからの暗黙的なスプーフィング保護 [だけが無効](email-validation-and-authentication.md#composite-authentication) にされます。 送信者がポリシーが検疫または拒否に設定されている場所で明示的な [DMARC](use-dmarc-to-validate-email.md) チェックに失敗した場合でも、メッセージは検疫または拒否されます。

  ブロックされたスプーフィングされた送信者からのメッセージの場合は、メッセージに対して実行するアクションを指定することもできます。

  - **[迷惑メール] フォルダーに** メッセージを移動する : これは既定値です。 メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。 Exchange Online では、メールボックスで迷惑メール ルールが有効になっている場合 (既定で有効になっている) 場合、メッセージは [迷惑メール] フォルダーに移動されます。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑](configure-junk-email-settings-on-exo-mailboxes.md)メール設定を構成する」を参照してください。

  - **メッセージを検疫する**: 意図した受信者の代わりにメッセージを検疫に送信します。 検疫の詳細については、次の記事を参照してください。

    - [Microsoft 365 での検疫](quarantine-email-messages.md)
    - [検疫済みメッセージとファイルを管理者として Microsoft 365 で管理する](manage-quarantined-messages-and-files.md)
    - [Microsoft 365 で検疫済みメッセージをユーザーとして検索して解放する](find-and-release-quarantined-messages-as-a-user.md)

- **認証されていない送信者:** 次のセクションの情報を参照してください。

### <a name="unauthenticated-sender"></a>認証されていない送信者

認証されていない送信者の識別は、前のセクションで[](#spoof-settings)説明したように、EOP および microsoft Defender for Office 365 のフィッシング対策ポリシーで使用可能なスプーフィング設定の一部です。

認証 **されていない送信者の設定では** 、Outlook で認証されていない送信者の識別を有効または無効にします。 具体的には次のとおりです。

- メッセージが SPF または DKIM チェックに合格しない場合に、メッセージが DMARC または複合認証に合格しない場合、送信者の写真に疑問符 (?) が[追加されます](email-validation-and-authentication.md#composite-authentication)。 認証されていない送信者の識別を無効にすると、送信者の写真に疑問符が追加されません。

- <u>差出</u>人アドレス (電子メール クライアントに表示されるメッセージ送信者) のドメインが、DKIM 署名または **MAIL FROM** アドレスのドメインと異なる場合は、via タグ (fabrikam.com 経由で chris@contoso.com) が追加されます。 これらのアドレスの詳細については、「電子メール メッセージ標準の [概要」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

  認証されていない送信者の識別を無効にしても、差出人アドレスのドメインが DKIM 署名または MAIL FROM アドレスのドメインと異なる場合は、via タグが追加されません。

疑問符またはタグが特定の送信者からのメッセージに追加されるのを防ぐには、次のオプションがあります。

- スプーフィング インテリジェンス ポリシーで送信者にスプーフィングを許可します。 このアクションを実行すると、認証されていない送信者の識別が無効な場合に、送信者からのメッセージに via タグが表示されません。 手順については [、「Microsoft 365 でスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。

- [送信者ドメインの電子](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) メール認証を構成します。
  - 送信者の写真の疑問符の場合、SPF または DKIM が最も重要です。
  - via タグの場合は、DKIM 署名内のドメイン、または **MAIL FROM** アドレスのドメインが From アドレス内のドメインと一致する (またはサブドメインである) か確認します。

詳細については、「Outlook on the web と Outlook.com [で不審なメッセージを識別する」を参照してください。](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの排他設定

このセクションでは、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用可能なポリシー設定について説明します。

> [!NOTE]
> Office 365 用 Microsoft Defender の既定のフィッシング対策ポリシー[](set-up-anti-phishing-policies.md#spoof-settings)は、すべての受信者にスプーフィング保護とメールボックス インテリジェンスを提供します。 ただし、その他の利用可能な [偽装保護](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 機能と [詳細設定](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) は、既定のポリシーでは構成または有効化されていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの偽装設定

偽装は、メッセージ内の送信者または送信者の電子メール ドメインが実際の送信者またはドメインに似ている場所です。

- ドメイン contoso.com のなりすまし例は óntoso.com です。
- ユーザー michelle@contoso.com のなりすまし例は、michele@contoso.com です。

なりすましされたドメインは、受信者を欺くことを目的とする場合を除いて、正規のドメイン（登録済みドメイン、構成済みの電子メール認証レコードなど）と見なされる場合があります。

次の偽装設定は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。

- **保護するユーザー**: 指定された内部または外部の電子メール アドレスがメッセージ送信者として偽装 **されるのを防ぐ**。 たとえば、社内の会社の副社長から社内情報の送信を求めるメール メッセージを受け取ります。 実行しますか? 多くのユーザーは、何も考えずに返信を送信します。

  保護されたユーザーを使用して、内部および外部の送信者の電子メール アドレスを追加し、偽装から保護できます。 このユーザー偽装から保護される送信者のリストは、ポリシーが適用される受信者の一覧 (既定のポリシーのすべての受信者、ポリシー設定セクションの [適用先] 設定で構成されている特定の受信者) とは異[](#policy-settings)なります。 

  > [!NOTE]
  >
  > - 各フィッシング対策ポリシーでは、最大 60 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。 複数のポリシーで同じ保護されたユーザーを指定できない。 したがって、受信者に適用されるポリシーの数に関係なく、個々の受信者の保護されたユーザー (送信者の電子メール アドレス) の最大数は 60 です。 ポリシーの優先度と、最初のポリシーを適用した後のポリシー処理の停止方法の詳細については、「電子メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。
  >
  > - 送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。 送信者と受信者が電子メールで通信したことがない場合、メッセージは偽装の試行として識別されます。

  既定では、保護するユーザーの偽装保護用に送信者の電子メール **アドレスは構成されていません**。 したがって、既定では、既定のポリシーまたはカスタム ポリシーでは、送信者の電子メール アドレスは偽装保護の対象とされません。

  内部または外部の電子メール アドレスを **ユーザー** に追加して保護する場合、それらの送信者からのメッセージは偽装保護チェックの対象になります。 メッセージがポリシーが適用される受信者(既定のポリシーのすべての受信者) にメッセージが送信された場合、メッセージは偽装のチェックを受け取ります。**カスタム ポリシー** 内の受信者に適用されます。 送信者の電子メール アドレスで偽装が検出されると、ユーザーの偽装保護アクションがメッセージに適用されます (メッセージの処理、偽装されたユーザーの安全性のヒントを表示するかどうかなど)。

- **保護するドメイン**: 指定されたドメインがメッセージ送信者のドメインで偽装されるの **を防ぐ**。 たとえば、所有しているすべてのドメイン[(承認](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)されたドメイン) や特定のドメイン (所有しているドメインまたはパートナー ドメイン) などです。 偽装から保護されている送信者ドメインのこのリストは、ポリシーが適用される受信者の一覧 (既定のポリシーのすべての受信者、ポリシー設定セクションの [適用先] 設定で構成されている特定の受信者) とは異[](#policy-settings)なります。 

  > [!NOTE]
  > すべてのフィッシング対策ポリシーで定義できる保護されたドメインの最大数は 50 です。

  既定では、保護するドメインの偽装保護用に構成 **された送信者ドメインはありません**。 したがって、既定では、既定のポリシーまたはカスタム ポリシーのいずれの送信者ドメインも偽装保護の対象とされません。

  ドメインをドメインに追加して保護リストを保護する場合、それらのドメインの送信者からのメッセージは偽装保護チェックの対象です。 メッセージがポリシーが適用される受信者(既定のポリシーのすべての受信者) にメッセージが送信された場合、メッセージは偽装のチェックを受け取ります。**カスタム ポリシー** 内の受信者に適用されます。 送信者のドメインで偽装が検出されると、ドメインの偽装保護アクションがメッセージに適用されます (メッセージの処理、偽装されたユーザーの安全性のヒントの表示など)。

- **保護されたユーザー** またはドメインのアクション : ポリシー内の保護されたユーザーおよび保護されたドメインに対する偽装試行を含む受信メッセージに対して実行するアクションを選択します。 保護されたユーザーの偽装と保護されたドメインの偽装に対して、さまざまなアクションを指定できます。

  - **アクションを適用しない**

  - **[メッセージを他の電子メール アドレスに** リダイレクトする]: 指定された受信者ではなく、指定した受信者にメッセージを送信します。

  - **[迷惑メール] フォルダーに** メッセージを移動する : メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。 Exchange Online では、メールボックスで迷惑メール ルールが有効になっている場合 (既定で有効になっている) 場合、メッセージは [迷惑メール] フォルダーに移動されます。 詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑](configure-junk-email-settings-on-exo-mailboxes.md)メール設定を構成する」を参照してください。

    - **メッセージを検疫する**: 意図した受信者の代わりにメッセージを検疫に送信します。 検疫の詳細については、次の記事を参照してください。

    - [Microsoft 365 での検疫](quarantine-email-messages.md)
    - [検疫済みメッセージとファイルを管理者として Microsoft 365 で管理する](manage-quarantined-messages-and-files.md)
    - [Microsoft 365 で検疫済みメッセージをユーザーとして検索して解放する](find-and-release-quarantined-messages-as-a-user.md)

  - **メッセージを配信し、BCC** 行に他のアドレスを追加します:メッセージを目的の受信者に配信し、指定された受信者にメッセージを通知しない方法で配信します。

  - **配信される前にメッセージを削除します**。メッセージ全体 (すべての添付ファイルを含む) をサイレント モードで削除します。

- **安全性のヒント**: 偽装チェックに失敗したメッセージが表示される、次の偽装安全性のヒントを有効または無効にします。

  - **偽装されたユーザー**: [From] アドレスに保護されたユーザーが含まれている。
  - **偽装ドメイン**: From アドレスに保護されたドメインが含まれている。
  - **通常とは** 異なる文字: 差出人アドレスには、保護された送信者またはドメインに通常とは異なる文字セット (たとえば、数学的記号とテキスト、大文字と小文字の組み合わせ) が含まれています。

  > [!IMPORTANT]
  >
  > 偽装の安全性のヒントがオフになっている場合でも、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用して、値が有効な **X-MS-Exchange-EnableFirstContactSafetyTip** という名前のメッセージ ヘッダーをメッセージに追加することを推奨します。 安全性のヒントは、受信者が初めて送信者からメッセージを受け取った場合、または送信者からメッセージを受け取らない場合に、受信者に通知します。
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="複数の受信者を含む偽装保護の安全のヒントのテキスト。":::

- **メールボックス インテリジェンス**: 頻繁に連絡先を持つユーザーの電子メール パターンを決定する人工知能 (AI) を有効または無効にします。 この設定は、AI が正当なメールとスプーフィングされた電子メールをそれらの連絡先と区別するのに役立ちます。 メールボックス インテリジェンスは、Exchange Online メールボックスでのみ使用できます。

- **メールボックス インテリジェンス ベースの偽装保護**: 各ユーザーの個々の送信者マップに基づいて拡張偽装結果を有効または無効にします。 このインテリジェンスにより、Microsoft 365 はユーザー偽装検出をカスタマイズし、誤検知をより適切に処理できます。 ユーザー偽装が検出されると、メッセージに対して実行する特定のアクションを定義できます。

  - **アクションを適用しない**
  - **メッセージを他のメール アドレスにリダイレクトする**
  - **メッセージを [迷惑メール] フォルダーに移動する**
  - **メッセージを検疫する**
  - **メッセージを配信し、BCC 行に他のアドレスを追加する**
  - **配信前にメッセージを削除する**

- **信頼できる送信者とドメイン**: 偽装保護設定の例外。 指定された送信者および送信者ドメインからのメッセージは、ポリシーによって偽装ベースの攻撃として分類されません。 つまり、保護された送信者、保護されたドメイン、またはメールボックス インテリジェンス保護のアクションは、これらの信頼できる送信者または送信者ドメインには適用されません。 これらのリストの最大数は、約 1000 エントリです。

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 のフィッシング対策ポリシーの高度なフィッシングしきい値

次の高度なフィッシングしきい値は、Microsoft Defender for Office 365 のフィッシング対策ポリシーでのみ使用できます。 これらのしきい値は、フィッシング判定を決定するために機械学習モデルをメッセージに適用する際の機性を制御します。

- **1 - 標準**: これは既定値です。 メッセージに対して実行されるアクションの重要度は、メッセージがフィッシングであるかどうか (低、中、高、または非常に高い信頼度) によって異なります。 たとえば、非常に高い信頼度を持つフィッシングとして識別されたメッセージは最も重大なアクションが適用される一方で、信頼度の低いフィッシングとして識別されたメッセージには、適用される重大なアクションが少ない場合があります。

- **2 - 積極的**: 信頼度の高いフィッシングとして識別されたメッセージは、非常に高い信頼度で識別された場合と同様に処理されます。

- **3 - より** 積極的: 中程度または高い信頼度を持つフィッシングとして識別されたメッセージは、非常に高い信頼度で識別されたと見なされます。

- **4 - 最** も積極的: 低、中、または高の信頼度を持つフィッシングとして識別されたメッセージは、非常に高い信頼度で識別されたと見なされます。

この設定を増やすと、誤検知 (良いメッセージが悪いとマークされる) の可能性が高まれます。 推奨設定の詳細については、Microsoft Defender のフィッシング対策ポリシーで [365 Officeを参照してください](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。
