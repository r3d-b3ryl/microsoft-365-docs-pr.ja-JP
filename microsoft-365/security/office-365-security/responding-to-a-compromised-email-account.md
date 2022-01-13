---
title: 侵害された電子メール アカウントへの対応
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.localizationpriority: high
search.appverid:
- MET150
description: Microsoft 365 で利用可能なツールを使用して、侵害された電子メール アカウントを認識して対処する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bdce44bc54c71d03e8064fa10187c06237d38b5b
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61941422"
---
# <a name="responding-to-a-compromised-email-account"></a>侵害された電子メール アカウントへの対応

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**概要** 侵害された Microsoft 365 電子メール アカウントを認識して対処する方法について説明します。

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>侵害された Microsoft 365 電子メール アカウントとは何か?

Microsoft 365 のメールボックス、データ、およびその他のサービスへのアクセスは、ユーザー名とパスワードや暗証番号 (PIN) などの資格情報を使用して制御されます。意図したユーザー以外の何者かがこれらの資格情報を盗んだ場合、盗まれた資格情報は侵害されたと見なされます。攻撃者は盗んだ資格情報を使用して、正規のユーザーとしてサインインし、不正な操作を行うことができます。

攻撃者は、盗んだ資格情報を使用して、ユーザーの Microsoft 365 メールボックス、SharePoint フォルダー、または OneDrive 内のファイルにアクセスできます。よく見られるのは、組織の内外の受信者に正規のユーザーとしてメールを送り付ける攻撃者です。データが攻撃者によって外部の受信者にメールで送信される事象をデータ流出と呼びます。

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>侵害された Microsoft メール アカウントの兆候

ユーザーが自分の Microsoft 365 メールボックスでの異常な活動に気付いて報告してくる場合があります。よく見られる兆候を以下に示します。

- 電子メールの消失や削除などの不審な活動。
- 侵害されたアカウントから電子メールを受信したが、その送信者の **送信済みアイテム** フォルダーに対応する電子メールが存在しない。
- 意図したユーザーまたは管理者が作成していない受信トレイ ルールの存在。このようなルールによって、自動的に不明なアドレスに電子メールが転送されたり、**メモ** フォルダー、**迷惑メール** フォルダー、または **RSS 購読** フォルダーに移動されたりする場合があります。
- グローバル アドレス一覧内のユーザーの表示名が変更される。
- ユーザーのメールボックスが電子メールの送信をブロックされる。
- Microsoft Outlook または Outlook on the web (旧名称は Outlook Web App) の送信済みアイテム フォルダーまたは削除済みアイテム フォルダーに "I'm stuck in London, send money" などのハッキングされたアカウント メッセージが格納される。
- 名前、電話番号、郵便番号などのめったに変更されないプロフィールが更新される。
- 複数のパスワードの変更など、異常な資格情報の変更が要求される。
- メールの転送が最近追加された。
- 偽の銀行署名や処方薬署名など、通常とは異なる署名が最近追加された。

ユーザーが上記の兆候のいずれかを報告してきた場合は、詳しい調査を実施する必要があります。 Microsoft 365 Defender ポータル と Azure ポータルには、侵害が疑われるユーザー アカウントの活動を調査するためのツールが用意されています。

- **Microsoft 365 Defender ポータルの統合監査ログ**: 不審な活動が発生する直前から現在の日付までの範囲で結果をフィルター処理することにより、疑わしいアカウントのすべての活動を確認します。 検索中にアクティビティをフィルター処理しないでください。 詳細については、「[コンプライアンス センターで監査ログを検索する](../../compliance/search-the-audit-log-in-security-and-compliance.md)」を参照してください。

- **Azure AD ポータルの Azure AD サインイン ログおよびその他のリスク レポート**: 次の列の値を調査します。
  - IP アドレスの確認
  - サインインの場所
  - サインインの時刻
  - サインインの成功/失敗

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>電子メール機能をセキュリティで保護し、侵害が疑われる Microsoft 365 アカウントとメールボックスを復元する方法

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

アカウントへのアクセスが回復されても、攻撃者がアカウントの制御を再開できるようなバック ドア エントリを追加している場合があります。

次の手順を最後まで実行して、できるだけ早くアカウントへのアクセスを回復し、乗っ取り犯がアカウントの制御を再開できないことを確認する必要があります。次の手順は、乗っ取り犯がアカウントに追加したかもしれないバック ドア エントリを削除できるように支援します。完了したら、ウイルス スキャンを実行してコンピューターが侵害されていないことを確認することをお勧めします。

### <a name="step-1-reset-the-users-password"></a>ステップ 1 ユーザーのパスワードをリセットする

「[誰かのビジネス パスワードをリセットする](../../admin/add-users/reset-passwords.md#reset-my-admin-password)」の手順に従います。

> [!IMPORTANT]
>
> - この時点ではまだ攻撃者がメールボックスへのアクセス権を握っている可能性があるため、意図したユーザーに新しいパスワードを電子メールで送信しないでください。
>
> - パスワードは、強力で、大文字と小文字、少なくとも 1 つの数字、および少なくとも 1 つの特殊文字が含まれていることを確認してください。
>
> - 直近の 5 つのパスワードのいずれかを再利用しないでください。パスワードの履歴要件によって最近のパスワードを再利用できる場合でも、攻撃者が推測できないパスワードを選択する必要があります。
>
> - オンプレミス ID が Microsoft 365 とフェデレーションされている場合は、パスワードをオンプレミスで変更してから、侵害を管理者に報告する必要があります。
>
> - アプリのパスワードは必ず更新してください。 ユーザー アカウントのパスワードをリセットしても、アプリのパスワードは自動的に取り消されません。 ユーザーは既存のアプリ パスワードを削除し、新しいパスワードを作成する必要があります。 手順については、「[追加セキュリティの検証ページでアプリのパスワードを作成して削除する](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)」を参照してください。
>
> - 特に、管理者特権を持っているアカウントの侵害を避けるために、多要素認証 (MFA) を有効にすることを強くお勧めします。 MFAの詳細については、[[多要素認証をセットアップする](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)] を参照してください。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>ステップ 2 不審な電子メール転送アドレスを削除する

1. <https://admin.microsoft.com> の Microsoft 365 管理センターで、**[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。 **アクティブ ユーザー** のページに直接移動するには <https://admin.microsoft.com/Adminportal/Home#/users> を使用します。

2. **アクティブ ユーザー** のページでは、問題のユーザ アカウントを検索し、チェックボックスをオンにせずにユーザー (行) を選択します。

3. 表示される詳細のポップアップで [**メール**] タブを選択します。

4. [**メール転送**] セクションの値が [**適用済み**] の場合、[**メールの転送を管理する**] をクリックします。 表示される [**メールの転送を管理する**] ポップアップで、[**このメールボックスに送信されたすべてのメールを転送する**] をオフにして、[**変更の保存**] をクリックします。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>ステップ 3 不審な受信トレイ ルールを無効にする

1. Outlook on the web を使用して、ユーザーのメールボックスにサインインします。

2. 歯車アイコンをクリックして、**[メール]** をクリックします。

3. **[受信トレイと一括処理ルール (Inbox and sweep rules)]** をクリックして、ルールを確認します。

4. 不審なルールを無効にするか、削除します。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>ステップ 4 ユーザーのメールの送信をブロック解除する

侵害が疑われるメールボックスがスパム メールを送信するために不正に使用された場合は、メールボックスのメールの送信がブロックされている可能性があります。

メールボックスのメールの送信をブロック解除するには、「[迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」の手順に従います。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>ステップ 5 オプション: ユーザー アカウントのサインインをブロックする

> [!IMPORTANT]
> アクセスを有効に戻しても安全なことが確認されるまでは、侵害が疑われるアカウントのサインインをブロックすることができます。

1. <https://admin.microsoft.com> の Microsoft 365 管理センターで、**[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。 **アクティブ ユーザー** のページに直接移動するには <https://admin.microsoft.com/Adminportal/Home#/users> を使用します。

2. **アクティブ ユーザー** のページでは、ユーザー アカウントを見つけて選択し、![[その他] のアイコン](../../media/ITPro-EAC-MoreOptionsIcon.png)をクリックして、**[サインイン状態の編集]** を選択します。

3. 表示される [**サインインをブロック**] ウィンドウで、[**このユーザーのサインインをブロックする**] を選択し、[**変更の保存**] をクリックします。

4. <https://admin.exchange.microsoft.com> の Exchange 管理センター (EAC) で、**[受信者]** \> **[メールボックス]** に移動します。 **[メールボックス]** ページに直接移動するには、<https://admin.exchange.microsoft.com/#/mailboxes> を使用します。

5. **[メールボックス]** ページで、ユーザーを見つけて選択します。 開いたメールボックスの詳細ポップアップで、次の手順を行います。
   - **[メール アプリ]** セクションで、**[メール アプリ設定の管理]** を選択します。 表示される「**メール アプリの設定の管理**」ポップアップで、トグルを右に動かして ![[無効]](../../media/scc-toggle-on.png) にし、利用可能なすべての設定をブロックします。
     - **Outlook on the web**
     - **Outlook デスクトップ (MAPI)**
     - **Exchange Web サービス**
     - **モバイル (Exchange ActiveSync)**
     - **IMAP**
     - **POP3**

   完了したら、**[保存]** をクリックしてから、**[閉じる]** をクリックします。

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>ステップ 6 オプション: すべての管理者役割グループから侵害が疑われるアカウントを削除する

> [!NOTE]
> 管理者役割グループ メンバーシップは、アカウントをセキュリティで保護した後に復元できます。

1. <https://admin.microsoft.com> の Microsoft 365 管理センターで、次の手順を実行します。
   1. [**ユーザー**]\>[**アクティブなユーザー**] の順に選択します。 **アクティブ ユーザー** のページに直接移動するには <https://admin.microsoft.com/Adminportal/Home#/users> を使用します。
   2. **アクティブ ユーザー** のページでは、ユーザー アカウントを見つけて選択し、![[その他] のアイコン](../../media/ITPro-EAC-MoreOptionsIcon.png)をクリックして、**[役割の管理]** を選択します。
   3. アカウントに割り当てられているすべての管理者の役割を削除します。 完了したら、[**変更の保存**] をクリックします。

2. <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開き、次の手順を行います。
   1. **[アクセス許可と役割]** \>>**[メールとコラボレーションの役割]** \>>**[役割]** の順に移動します。 **"アクセス許可"** ページに直接移動するには、<https://security.microsoft.com/emailandcollabpermissions> を使用します。
   2. **[アクセス許可]** ページで、リストから各役割グループを選択して、表示される詳細ポップアップの **[メンバー]** セクションでユーザー アカウントを検索します。役割グループにユーザー アカウントが含まれている場合は、次の手順を実行します。
      1. [**メンバー**] セクションの [**編集**] をクリックします。
      2. **[メンバーの選択の編集]** のポップアップが表示されたら、**[編集]** をクリックします。
      3. **[メンバーの選択]** のポップアップが表示されたら、**[削除]** をクリックします。
      4. ポップアップが表示されたら、ユーザー アカウントを選択し、**[削除]** をクリックします。

         完了したら、**[完了]**、**[保存]**、**[閉じる]** の順にクリックします。

3. <https://admin.exchange.microsoft.com/> で Exchange 管理センターを使用して、次の手順に進みます。
   1. **[役割]** \>> **[管理者の役割]** の順に選択します。 **[管理者の役割]** ページに直接移動するには、<https://admin.exchange.microsoft.com/#/adminRoles> を使用します。
   2. **[管理者の役割]** ページで、各役割グループを手動で選択し、詳細ウィンドウの **[割り当て]** タブでユーザー アカウントを確認します。 役割グループにユーザー アカウントが含まれている場合は、次の手順を実行します。
      1. ユーザー アカウントを選択します。
      2. 登録するには、このページの上方にある ![[削除] アイコン。](../../media/m365-cc-sc-delete-icon.png).

         完了したら、**[保存]** をクリックします。

### <a name="step-7-optional-additional-precautionary-steps"></a>ステップ 7 オプション: その他の予防手順

1. 送信済みアイテムを確認します。連絡先リストに掲載されている人にアカウントが侵害されたことを通知する必要があります。攻撃者は、彼らにお金を要求したり、あなたが外国で足留めされ、お金が必要だなどと偽ったり、彼らにウイルスを送り付けて彼らのコンピューターも乗っ取ろうとしたりする可能性があります。

2. この Exchange アカウントを代替電子メール アカウントとして使用していた他のサービスが侵害されている場合があります。まず、Microsoft 365 サブスクリプションに対してこれらの手順を実行してから、その他のアカウントに対してこれらの手順を実行します。

3. 電話番号や住所などの連絡先情報が正しいことを確認します。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- 最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。
- 最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。
- 90 日以降。最初の 90 日間の作業で保護が強化されます。

## <a name="see-also"></a>関連項目

- [Microsoft 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う](detect-and-remediate-outlook-rules-forms-attack.md)
- [米国インターネット犯罪苦情センター](https://www.ic3.gov/Home/Ransomware)
- [米国証券取引委員会 - "フィッシング" 詐欺](https://www.sec.gov/investor/pubs/phishing.htm)
- 迷惑メールを Microsoft および管理者に直接報告する場合に[迷惑メール報告アドインを使用する](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
