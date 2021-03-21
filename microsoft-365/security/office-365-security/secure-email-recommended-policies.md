---
title: セキュリティで保護された電子メール推奨ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 9a47789c48fa35335430d342948dfdad1b32e7bf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917334"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)


この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨される ID およびデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは、共通 [ID](identity-access-policies.md) とデバイス アクセス ポリシーに基いて作成され、さらにいくつかの推奨事項も含まれています。

これらの推奨事項は、ニーズの粒度に基づいて適用できる 3 つの異なるセキュリティ層と保護に基づいて行います。ベースライン、機密性の高い、高度に **規制されています**。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、ユーザーがモバイル デバイスで Outlook for iOS や Android などの最新のメール クライアントを使用する必要があります。 Outlook for iOS と Android は、365 の最適な機能をサポートOfficeします。 これらのモバイル Outlook アプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と共に動作するセキュリティ機能も備えた設計されています。 詳細については [、「Outlook for iOS および Android FAQ」を参照してください](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。

## <a name="update-common-policies-to-include-email"></a>電子メールを含める一般的なポリシーを更新する

電子メールを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。

[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

ActiveSync クライアントをブロックする Exchange Online の新しいポリシーの追加に注意してください。 これにより、Outlook モバイルが強制的に使用されます。

ポリシーを設定するときにポリシーのスコープに Exchange Online と Outlook を含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。 次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。 各ポリシーは、共通 ID およびデバイス アクセス ポリシーの関連する [構成手順にリンクします](identity-access-policies.md)。

|保護レベル|Policies|詳細|
|---|---|---|
|**Baseline**|[サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに Exchange Online を含める|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てに Exchange Online を含める|
||[APP データ保護ポリシーの適用](identity-access-policies.md#apply-app-data-protection-policies)|Outlook がアプリの一覧に含まれているか確認してください。 各プラットフォームのポリシーを必ず更新してください (iOS、Android、Windows)|
||[承認済みアプリと APP 保護を要求する](identity-access-policies.md#require-approved-apps-and-app-protection)|クラウド アプリの一覧に Exchange Online を含める|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウド アプリの一覧に Exchange Online を含める|
||[ActiveSync クライアントのブロック](#block-activesync-clients)|この新しいポリシーを追加する|
|**機密**|[サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに Exchange Online を含める|
||[準拠している PC とモバイル *デバイスを* 要求する](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド アプリの一覧に Exchange Online を含める|
|**厳しく規制**|[*常に* MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てに Exchange Online を含める|
|

## <a name="block-activesync-clients"></a>ActiveSync クライアントのブロック

このポリシーにより、ActiveSync クライアントは他の条件付きアクセス ポリシーをバイパスしません。 ポリシー構成は ActiveSync クライアントにのみ適用されます。 [アプリ保護ポリシーを **[要求する] を選択すると、ActiveSync](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** クライアントがブロックされます。 このポリシーの作成の詳細については、「条件付きアクセスを使用したクラウド アプリ アクセスのアプリ保護ポリシーを要求 [する」を参照してください](/azure/active-directory/conditional-access/app-protection-based-conditional-access)。

- シナリオ [1: Office 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)アプリでは、基本認証を利用する Exchange ActiveSync クライアントが Exchange Online に接続することを防止する、アプリ保護ポリシーを持つ承認済みアプリが必要です。「手順 2: ActiveSync (EAS)を使用して Exchange Online 用の Azure AD 条件付きアクセス ポリシーを構成する」に従います。

また、認証ポリシーを使用して基本[](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Outlook on the web から Exchange Online へのアクセスを制限する

ユーザーが umnanaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。 これらのデバイス上のユーザーは、デバイスにファイルを漏洩して保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。 ユーザーが管理されていないデバイスで添付ファイルを見るのをブロックすることもできます。

それらのステップは次のとおりです。

1. [Exchange Online リモート PowerShell セッションに接続します](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。
2. OWA メールボックス ポリシーをまだ持ってない場合は [、New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して作成します。
3. 添付ファイルの表示を許可するが、ダウンロードを許可する場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. 添付ファイルをブロックする場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Azure portal で、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。

   **割り当て** \>**ユーザーとグループ**: 含めるおよび除外する適切なユーザーとグループを選択します。

   **割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**Include** \>**アプリの選択**: **365 Exchange Online Officeを選択する**

   **アクセス制御** \>**セッション**: [アプリ **の適用制限を使用する] を選択します。**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>iOS デバイスと Android デバイスで Outlook を使用する必要がある

iOS および Android デバイスのユーザーが、Outlook for iOS および Android を使用して仕事または学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。

「Outlook for iOS および Android を使用してメッセージング コラボレーション アクセスを管理する」でこのポリシーを構成する手順 [を参照してください]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。

## <a name="set-up-message-encryption"></a>メッセージの暗号化を設定する

Azure Information Protection のOffice機能を活用する新しい 365 メッセージ暗号化 (OME) 機能を使用すると、組織は保護された電子メールを任意のデバイスの誰とでも簡単に共有できます。 ユーザーは、保護されたメッセージを他の Microsoft 365 組織、およびユーザー以外のユーザーと送受信して、Outlook.com、Gmail、その他の電子メール サービスを使用できます。

詳細については、「Set [up new Office 365 Message Encryption capabilitis 」を参照してください](../../compliance/set-up-new-message-encryption-capabilities.md)。

## <a name="next-steps"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセス ポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)