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
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) および Microsoft Defender for Office 365 で使用できるフィッシング対策ポリシーについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe7d986c537cbc5da31811e0b49cf6224815d32c
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509316"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a>Microsoft 365 のフィッシング対策ポリシー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

フィッシング対策の保護設定を構成するポリシーは、Exchange Online メールボックスを使用する Microsoft 365 組織、Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織、および Office 365 組織向け Microsoft Defender で利用できます。

Microsoft Defender for Office 365 のフィッシング対策ポリシーは、365 の Defender を持つ組織でのみOfficeできます。 例:

- Microsoft 365 Enterprise E5、Microsoft 365 Education A5 など
- [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home)
- [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)
- [Microsoft Defender for Office 365 をアドオンとして使用する](https://products.office.com/exchange/advance-threat-protection)

次の表に、EOP のフィッシング対策ポリシーと microsoft Defender for Office 365 のフィッシング対策ポリシーの大きな違いについて説明します。

****

|機能|EOP のフィッシング対策ポリシー|Microsoft Defender のフィッシング対策ポリシー (Office 365)|
|---|:---:|:---:|
|既定のポリシーを自動的に作成する|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|カスタム ポリシーの作成|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|ポリシー設定<sup>\*</sup>|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|偽装設定||![チェック マーク](../../media/checkmark.png)|
|スプーフィング設定|![チェック マーク](../../media/checkmark.png)|![チェック マーク](../../media/checkmark.png)|
|高度なフィッシングのしきい値||![チェック マーク](../../media/checkmark.png)|
|

<sup>\*</sup> 既定のポリシーでは、ポリシー名と説明は読み取り専用です (説明は空白です)、ポリシーを適用するユーザーを指定することはできません (既定のポリシーはすべての受信者に適用されます)。

フィッシング対策ポリシーを構成するには、次の記事を参照してください。

- [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)

- [Microsoft Defender でフィッシング対策ポリシーを構成する (Office 365)](configure-atp-anti-phishing-policies.md)

この記事の残りの部分では、EOP および Defender for Office 365 のフィッシング対策ポリシーで使用できる設定について説明します。

## <a name="policy-settings"></a>ポリシー設定

EOP および Microsoft Defender のフィッシング対策ポリシーでは、次のポリシー設定を使用Office 365 です。

- **名前**: 既定のフィッシング対策ポリシーの名前を変更できない。 カスタムフィッシング対策ポリシーを作成した後は、セキュリティ コンプライアンス センターでポリシーの&変更できます。

- **説明** 既定のフィッシング対策ポリシーには説明を追加できますが、作成するカスタム ポリシーの説明を追加および変更できます。

- **適用対象**: フィッシング対策ポリシーが適用される内部受信者を識別します。 この値はカスタム ポリシーで必須であり、既定のポリシーでは使用できません (既定のポリシーはすべての受信者に適用されます)。

  各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。 同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。 a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。

  - **受信者:** 組織内の 1 つ以上のメールボックス、メール ユーザー、またはメール連絡先。
  - **受信者は、組織内の** 1 つ以上のグループのメンバーです。
  - **受信者ドメインは、Microsoft** 365 で構成されている 1 つ以上の受け入れ可能なドメインです。

  - **:ルール** の例外を除く。 設定と動作は、次の条件とまったく同じになります。

    - **受信者が**
    - **受信者は、**
    - **受信者ドメインは、**

  > [!NOTE]
  > ポリシー **が適用される** メッセージ受信者を識別するには、カスタムフィッシング対策ポリシーで [適用先]<u>設定が必要です</u>。 microsoft Defender for Office 365 のフィッシング対策ポリシーには、この[](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)記事で後述する偽装保護を受ける送信者の電子メール アドレス<u></u>または送信者ドメインを個別に指定できる偽装設定があります。

## <a name="spoof-settings"></a>スプーフィング設定

スプーフィングは、電子メール メッセージの From アドレス (電子メール クライアントに表示される送信者アドレス) が電子メール ソースのドメインと一致しない場合です。 スプーフィングの詳細については [、「Microsoft 365](anti-spoofing-protection.md)でのスプーフィング防止保護」を参照してください。

EOP および Microsoft Defender のフィッシング対策ポリシーでは、次のスプーフィング設定を使用できます(Office 365)

- **スプーフィング対策保護**: スプーフィング対策保護を有効または無効にします。 有効のままにすることをお勧めします。 スプーフィング **インテリジェンス ポリシーを使用して** 、特定のスプーフィングされた内部および外部の送信者を許可またはブロックします。 詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。

  > [!NOTE]
  >
  > - スプーフィング対策保護は、既定のフィッシング対策ポリシーと、作成した新しいカスタムフィッシング対策ポリシーで既定で有効になっています。
  >
  > - MX レコードが Microsoft 365 をポイントしない場合は、スプーフィング防止保護を無効にする必要があります。代わりに、コネクタの拡張フィルターを有効にできます。 手順については [、「Enhanced Filtering for Connectors in Exchange Online」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。
  >
  > - スプーフィング対策保護を無効にすると、複合認証チェックからの暗黙的なスプーフィング [保護だけが無効](email-validation-and-authentication.md#composite-authentication) にされます。 送信者が明示的な [DMARC](use-dmarc-to-validate-email.md) に失敗した場合、ポリシーが検疫または拒否に設定されている場所を確認しても、メッセージは検疫または拒否されます。

  ブロックされたスプーフィングされた送信者からのメッセージの場合は、メッセージに対して実行するアクションを指定することもできます。

  - **[メッセージを迷惑メール フォルダーに移動]:** これが既定値です。 メッセージはメールボックスに配信され、迷惑メール フォルダーに移動されます。 Exchange Online では、メールボックスで迷惑メール ルールが有効になっている場合 (既定で有効になっている) 場合、メッセージは迷惑メール フォルダーに移動されます。 詳細については [、「Microsoft 365 の Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)メールボックスで迷惑メール設定を構成する」を参照してください。

  - **メッセージを検疫する**: メッセージを目的の受信者ではなく検疫に送信します。 検疫の詳細については、次の記事を参照してください。

    - [Microsoft 365 の検疫](quarantine-email-messages.md)
    - [Microsoft 365 で検疫済みメッセージとファイルを管理者として管理する](manage-quarantined-messages-and-files.md)
    - [Microsoft 365 で検疫済みメッセージをユーザーとして検索して解放する](find-and-release-quarantined-messages-as-a-user.md)

- **認証されていない送信者 :** 次のセクションの情報を参照してください。

### <a name="unauthenticated-sender"></a>認証されていない送信者

認証されていない送信者の識別は、前のセクションで[](#spoof-settings)説明したように、EOP および Microsoft Defender for Office 365 のフィッシング対策ポリシーで使用できるスプーフィング設定の一部です。

[ **認証されていない送信者] 設定では** 、Outlook で認証されていない送信者の識別を有効または無効にします。 具体的には次のとおりです。

- メッセージが SPF または DKIM チェックに合格しない場合に、メッセージが DMARC または複合認証に合格しない場合、送信者の写真に疑問符 (?) が[追加されます](email-validation-and-authentication.md#composite-authentication)。 認証されていない送信者の識別を無効にすると、送信者の写真に疑問符が追加されません。

- <u>差出</u>人アドレス (電子メール クライアントに表示されるメッセージ送信者) のドメインが DKIM 署名または MAIL FROM アドレスのドメインと異なる場合は、via タグ (fabrikam.com 経由で chris@contoso.com) が **追加** されます。 これらのアドレスの詳細については、「電子メール [メッセージ標準の概要」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

  認証されていない送信者 ID を無効にしても、差出人アドレスのドメインが DKIM 署名または MAIL FROM アドレスのドメインと異なる場合、via タグが追加されません。

疑問符またはタグ経由で特定の送信者からのメッセージに追加されるのを防ぐには、次のオプションがあります。

- スプーフィング インテリジェンス ポリシーで送信者にスプーフィングを許可します。 このアクションでは、認証されていない送信者の識別が無効になっているときに、送信者からのメッセージに via タグが表示されません。 手順については、「Configure スプーフィング インテリジェンス in [Microsoft 365」を参照してください](learn-about-spoof-intelligence.md)。

- [送信者ドメインの電子](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) メール認証を構成します。
  - 送信者の写真の疑問符では、SPF または DKIM が最も重要です。
  - via タグの場合は、DKIM 署名のドメインまたは **MAIL FROM** アドレスが From アドレスのドメインと一致 (またはサブドメイン) を確認します。

詳細については、「Web での不審なメッセージの識別 [Outlook.com Outlook on the web」を参照してください。](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)

## <a name="exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーの排他的設定 (Office 365)

このセクションでは、Microsoft Defender のフィッシング対策ポリシーでのみ使用できるポリシー設定について説明し、Officeします。

> [!NOTE]
> Microsoft Defender for Office 365 の既定のフィッシング対策ポリシー[](set-up-anti-phishing-policies.md#spoof-settings)は、すべての受信者にスプーフィング保護とメールボックス インテリジェンスを提供します。 ただし、既定のポリシーでは、[他の](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)利用可能[](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)な偽装保護機能と高度な設定が構成または有効になっていません。 すべての保護機能を有効にするには、既定のフィッシング対策ポリシーを変更するか、追加のフィッシング対策ポリシーを作成します。

### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーの偽装設定 (Office 365)

偽装とは、メッセージ内の送信者または送信者の電子メール ドメインが実際の送信者またはドメインに似ている場合です。

- ドメイン contoso.com のなりすまし例は óntoso.com です。
- ユーザー michelle@contoso.com のなりすまし例は、michele@contoso.com です。

なりすましされたドメインは、受信者を欺くことを目的とする場合を除いて、正規のドメイン（登録済みドメイン、構成済みの電子メール認証レコードなど）と見なされる場合があります。

次の偽装設定は、Microsoft Defender のフィッシング対策ポリシー (365 の場合) でのみOfficeできます。

- **保護するユーザー**: 指定された内部または外部の電子メール アドレスがメッセージ送信者として偽装 **されるのを防ぐ**。 たとえば、会社のバイスプレジデントから社内情報の送信を求める電子メール メッセージを受け取ります。 やってみませんか? 多くの人が何も考えずに返信を送るでしょう。

  保護されたユーザーを使用して、偽装から保護するために内部および外部の送信者の電子メール アドレスを追加できます。 このユーザー偽装から保護される送信者の一覧は、ポリシーが適用される受信者の一覧 (既定のポリシーのすべての受信者、ポリシー設定セクションの [適用先] 設定で構成されている特定の受信者) とは[](#policy-settings)異なります。 

  > [!NOTE]
  >
  > - 各フィッシング対策ポリシーでは、最大 60 人の保護されたユーザー (送信者の電子メール アドレス) を指定できます。 複数のポリシーで同じ保護されたユーザーを指定できない。 したがって、受信者に適用されるポリシーの数に関係なく、個々の受信者の保護されたユーザー (送信者の電子メール アドレス) の最大数は 60 です。 ポリシーの優先度と、最初のポリシーの適用後にポリシー処理が停止する方法の詳細については、「電子メール保護の順序と優先順位」 [を参照してください](how-policies-and-protections-are-combined.md)。
  >
  > - 送信者と受信者が以前に電子メールで通信した場合、ユーザー偽装保護は機能しません。 送信者と受信者がメールで通信したことがない場合、メッセージは偽装の試みとして識別されます。

  既定では、ユーザーの偽装保護用に送信者の電子メール アドレス **が構成されていません**。 したがって、既定では、送信者の電子メール アドレスは、既定のポリシーまたはカスタム ポリシーの偽装保護によってカバーされません。

  内部または外部の電子メール アドレスを **ユーザー** に追加してリストを保護すると、それらの送信者からのメッセージは偽装保護チェックの対象になります。 ポリシーが適用される受信者 (既定のポリシーのすべての受信者)にメッセージが送信された場合、メッセージは偽装のチェックを受け取ります。**カスタム ポリシー** の受信者に適用されます)。 送信者の電子メール アドレスで偽装が検出された場合、ユーザーの偽装保護アクションがメッセージに適用されます (メッセージの処理、偽装ユーザーの安全に関するヒントの表示など)。

- **保護するドメイン**: 指定したドメインがメッセージ送信者のドメインで偽装されるの **を防ぐ**。 たとえば、所有しているすべてのドメイン[(受](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)け入れドメイン) または特定のドメイン (所有しているドメインまたはパートナー ドメイン)。 偽装から保護される送信者ドメインのこのリストは、ポリシーが適用される受信者の一覧 (既定のポリシーのすべての受信者、ポリシー設定セクションの [適用先] 設定で構成されている特定の受信者) とは異[](#policy-settings)なります。 

  > [!NOTE]
  > すべてのフィッシング対策ポリシーで定義できる保護されたドメインの最大数は 50 です。

  既定では、保護するドメインの偽装保護用に送信者 **ドメインは構成されていません**。 したがって、既定では、既定のポリシーまたはカスタム ポリシーでは、偽装保護の対象となる送信者ドメインはありません。

  ドメインをドメインに追加してリストを保護すると、それらのドメインの送信者からのメッセージは偽装保護チェックの対象です。 ポリシーが適用される受信者 (既定のポリシーのすべての受信者)にメッセージが送信された場合、メッセージは偽装のチェックを受け取ります。**カスタム ポリシー** の受信者に適用されます)。 送信者のドメインで偽装が検出された場合、ドメインの偽装保護アクションがメッセージに適用されます (メッセージの処理、偽装ユーザーの安全に関するヒントの表示など)。

- **保護されたユーザー** またはドメインのアクション: ポリシー内の保護されたユーザーと保護されたドメインに対する偽装の試行を含む受信メッセージに対して実行するアクションを選択します。 保護されたユーザーの偽装と保護されたドメインの偽装に対して、さまざまなアクションを指定できます。

  - **アクションを適用しない**

  - **メッセージを他の電子メール アドレス** にリダイレクトする: メッセージを、目的の受信者ではなく、指定した受信者に送信します。

  - **[メッセージを迷惑メール フォルダーに** 移動]: メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。 Exchange Online では、メールボックスで迷惑メール ルールが有効になっている場合 (既定で有効になっている) 場合、メッセージは迷惑メール フォルダーに移動されます。 詳細については [、「Microsoft 365 の Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)メールボックスで迷惑メール設定を構成する」を参照してください。

    - **メッセージを検疫する**: メッセージを目的の受信者ではなく検疫に送信します。 検疫の詳細については、次の記事を参照してください。

    - [Microsoft 365 の検疫](quarantine-email-messages.md)
    - [Microsoft 365 で検疫済みメッセージとファイルを管理者として管理する](manage-quarantined-messages-and-files.md)
    - [Microsoft 365 で検疫済みメッセージをユーザーとして検索して解放する](find-and-release-quarantined-messages-as-a-user.md)

  - **メッセージを配信し、他** のアドレスを Bcc 行に追加する : メッセージを目的の受信者に配信し、指定した受信者にメッセージをサイレント配信します。

  - **配信前にメッセージを削除する**: メッセージ全体 (すべての添付ファイルを含む) をサイレントモードで削除します。

- **安全に関する** ヒント: 偽装チェックに失敗したメッセージが表示される、次の偽装安全ヒントを有効または無効にします。

  - **偽装ユーザー**: From アドレスには、保護されたユーザーが含まれる。
  - **偽装ドメイン**: From アドレスには保護されたドメインが含まれる。
  - **異常な** 文字 : 差出人アドレスには、保護された送信者またはドメインに、通常とは異なる文字セット (数学記号とテキスト、大文字と小文字の組み合わせなど) が含まれています。


  > [!IMPORTANT]
  >
  > 送信者と受信者の間の初回の連絡先の間に表示される安全ヒントを有効にするための推奨事項 **:** 偽装の安全ヒントがオフになっている場合でも、メールフロー ルール (トランスポート ルールとも呼ばれる) を使用して、値が有効な **X-MS-Exchange-EnableFirstContactSafetyTip** という名前のメッセージ ヘッダーをメッセージに追加することをお勧めします。 安全上のヒントは、送信者から初めてメッセージを受け取った場合、または送信者からメッセージを受け取らない場合に、受信者に通知します。 この機能は、潜在的な偽装攻撃に対するセキュリティ保護の層を追加します。 
  > :::image type="content" source="../../media/safety-tip-first-contact-multiple-recipients.png" alt-text="複数の受信者による偽装保護の安全ヒントのテキスト。":::

- **メールボックス インテリジェンス**: 頻繁に連絡先を持つユーザーのメール パターンを決定する人工知能 (AI) を有効または無効にします。 この設定は、AI が正当なメールとスプーフィングされたメールとそれらの連絡先を区別するのに役立ちます。 メールボックス インテリジェンスは、Exchange Online メールボックスでのみ使用できます。

- **メールボックス インテリジェンス ベースの偽装保護**: 各ユーザーの個々の送信者マップに基づいて、拡張偽装結果を有効または無効にします。 このインテリジェンスにより、Microsoft 365 はユーザー偽装検出をカスタマイズし、誤検知をより適切に処理できます。 ユーザー偽装が検出されると、メッセージに対して実行する特定のアクションを定義できます。

  - **アクションを適用しない**
  - **メッセージを他の電子メール アドレスにリダイレクトする**
  - **メッセージを迷惑メール フォルダーに移動する**
  - **メッセージを検疫する**
  - **メッセージを配信し、他のアドレスを Bcc 行に追加する**
  - **配信前にメッセージを削除する**

- **信頼できる送信者とドメイン**: 偽装保護設定の例外。 指定された送信者および送信者ドメインからのメッセージは、ポリシーによって偽装ベースの攻撃として分類されません。 つまり、保護された送信者、保護されたドメイン、またはメールボックス インテリジェンス保護のアクションは、これらの信頼できる送信者または送信者ドメインには適用されません。 これらのリストの最大制限は、約 1000 エントリです。

### <a name="advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender のフィッシング対策ポリシーの高度なフィッシングしきい値 (Office 365)

次の高度なフィッシング詐欺のしきい値は、Microsoft Defender のフィッシング対策ポリシーで、Office 365 でのみ使用できます。 これらのしきい値は、フィッシングの判定を決定するためのメッセージに機械学習モデルを適用する際の感度を制御します。

- **1 - Standard**: これが既定値です。 メッセージに対して実行されるアクションの重大度は、メッセージがフィッシング (低、中、高、または非常に高い信頼) であるという信頼度によって異なります。 たとえば、信頼度が非常に高いフィッシング詐欺として識別されるメッセージは最も重大なアクションを適用しますが、信頼度の低いフィッシングとして識別されるメッセージは、より厳しいアクションが適用されません。

- **2 - アグレッ** シブ : 高い信頼度を持つフィッシングと識別されたメッセージは、非常に高い信頼性で識別された場合と同様に処理されます。

- **3 - より** 積極的: 中程度または高い信頼度を持つフィッシングとして識別されるメッセージは、非常に高い信頼度で識別された場合と同様に処理されます。

- **4 - 最** も攻撃的: 信頼度が低い、中程度、または高い信頼性を持つフィッシングとして識別されるメッセージは、非常に高い信頼度で識別された場合と同様に処理されます。

この設定を増やすと、誤検知 (良いメッセージが正しいとマークされている) の可能性が高くなっています。 推奨設定の詳細については、「Microsoft Defender のフィッシング対策ポリシー」を参照Office [365 の設定を参照してください](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。
