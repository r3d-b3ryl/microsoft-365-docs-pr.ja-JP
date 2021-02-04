---
title: セキュリティで保護された電子メールの推奨ポリシー - Microsoft 365 enterprise |Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 261c375aa17e4a3bc8f7d1b469d82621cf4ae45b
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097130"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨される ID およびデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは、共通 [ID](identity-access-policies.md) ポリシーとデバイス アクセス ポリシーに基じ、さらにいくつかの推奨事項も示します。

これらの推奨事項は、ニーズの粒度に基づいて適用できる 3 つの異なる層のセキュリティと保護に基づいており、ベースライン、機密、厳しく規制 **されています**。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、ユーザーがモバイル デバイスで iOS および Android 用の Outlook を含む最新の電子メール クライアントを使用する必要があります。 iOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。 これらのモバイル Outlook アプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と一緒に動作するセキュリティ機能を使用して設計されています。 詳細については [、iOS および Android 用の Outlook に関する FAQ を参照してください](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。

## <a name="update-common-policies-to-include-email"></a>電子メールを含める一般的なポリシーを更新する

電子メールを保護するために、次の図は、共通 ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。

[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[このイメージのより大きなバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

ActiveSync クライアントをブロックする Exchange Online の新しいポリシーの追加に注意してください。 これにより、Outlook モバイルが強制的に使用されます。

ポリシーのセットアップ時にポリシーのスコープに Exchange Online と Outlook を含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。 次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。 各ポリシーは、共通 ID ポリシーとデバイス アクセス ポリシーに関連 [する構成手順にリンクします](identity-access-policies.md)。

|保護レベル|Policies|詳細|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに Exchange Online を含める|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに Exchange Online を含める|
||[アプリ のデータ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|Outlook がアプリの一覧に含まれている必要があります。 各プラットフォーム (iOS、Android、Windows) のポリシーを必ず更新してください。|
||[承認されたアプリとアプリの保護を要求する](identity-access-policies.md#require-approved-apps-and-app-protection)|クラウド アプリの一覧に Exchange Online を含める|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウド アプリの一覧に Exchange Online を含める|
||[ActiveSync クライアントをブロックする](#block-activesync-clients)|この新しいポリシーを追加する|
|**機密**|[サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに Exchange Online を含める|
||[準拠した PC とモバイル *デバイスが* 必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド アプリの一覧に Exchange Online を含める|
|**厳しく規制**|[*常に* MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに Exchange Online を含める|
|

## <a name="block-activesync-clients"></a>ActiveSync クライアントをブロックする

このポリシーにより、ActiveSync クライアントは他の条件付きアクセス ポリシーをバイパスしません。 ポリシー構成は ActiveSync クライアントにのみ適用されます。 [アプリ保護ポリシーを **[要求する] を選択](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** すると、このポリシーは ActiveSync クライアントをブロックします。 このポリシーの作成に関する詳細については、「条件付きアクセスによるクラウド アプリ アクセスのアプリ保護ポリシーを要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)。

- シナリオ [1: Office 365](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリでは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続することを防ぐ、アプリ保護ポリシーを持つ承認されたアプリが必要です。シナリオ 1 の「手順 2: ActiveSync (EAS) を使用して Exchange Online 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。

また、認証ポリシーを使用して基本[](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Outlook on the web からの Exchange Online へのアクセスを制限する

ユーザーが Umaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。 これらのデバイス上のユーザーは、デバイスにファイルをリークして保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。 管理されていないデバイスでユーザーに添付ファイルが表示されるのをブロックすることもできます。

それらのステップは次のとおりです。

1. [Exchange Online リモート PowerShell セッションに接続します](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。
2. OWA メールボックス ポリシーをまだ持ってない場合は [、New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して OWA メールボックス ポリシーを作成します。
3. 添付ファイルの表示を許可し、ダウンロードを許可する場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. 添付ファイルをブロックする場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Azure portal で、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。

   **割り当て** \>**ユーザーとグループ**: 含める、または除外する適切なユーザーとグループを選択します。

   **割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**含める** \>**アプリの選択**: Office **365 Exchange Online を選択する**

   **アクセス制御** \>**セッション**: [アプリによって **適用される制限を使用する] を選択する**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>iOS デバイスと Android デバイスで Outlook を使用する必要がある

iOS および Android デバイスのユーザーが、iOS および Android 用の Outlook を使用して仕事や学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。

このポリシーを構成する手順については、「iOS および Android 用の Outlook を使用してメッセージングコラボレーション アクセス [を管理する」を参照してください]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。

## <a name="set-up-message-encryption"></a>メッセージの暗号化を設定する

Azure Information Protection の保護機能を活用する新しい Office 365 Message Encryption (OME) 機能を使用すると、組織は保護された電子メールを任意のデバイスのすべてのユーザーと簡単に共有できます。 ユーザーは、他の Microsoft 365 組織だけでなく、Outlook.com、Gmail、その他のメール サービスを使用して、保護されたメッセージを送受信できます。

詳細については [、「Set up new Office 365 Message Encryption capabilities 」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)。

## <a name="next-steps"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件に合ったアクセス ポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
