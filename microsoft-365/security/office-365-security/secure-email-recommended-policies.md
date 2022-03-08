---
title: セキュリティで保護された電子メール推奨ポリシー - エンタープライズ Microsoft 365の|Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: b708d7aa993bdcd74b6fe00f633e3f7933ff04b8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321741"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

この記事では、最新の認証と条件付きアクセスをサポートする組織の電子メール および電子メール クライアントを保護するために、推奨されるゼロトラスト ID およびデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは、共通 ID とデバイス アクセス ポリシーに基いて [作成](identity-access-policies.md) され、さらにいくつかの推奨事項も含まれています。

これらの推奨事項は、ニーズの細分性に基づいて適用できる 3 つの異なるレベルのセキュリティと保護に基づいて行います。開始点、エンタープライズ、および特殊な **セキュリティ。** これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、ユーザーがモバイル デバイス上の iOS および Android のOutlookなど、最新のメール クライアントを使用する必要があります。 Outlook iOS と Android のサポートは、アプリの最適な機能をサポートOffice 365。 これらのモバイル Outlookアプリは、モバイルの使用をサポートし、他の Microsoft クラウド セキュリティ機能と共に動作するセキュリティ機能も備えた設計されています。 詳細については、「[iOS Outlook Android FAQ」を参照してください](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)。

## <a name="update-common-policies-to-include-email"></a>電子メールを含める一般的なポリシーを更新する

電子メールを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーから更新するポリシーを示しています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png" alt-text="アクセスを保護するためのポリシー更新プログラムの概要Exchange。" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png":::

ActiveSync クライアントをブロックする新しいポリシー Exchange Onlineに注意してください。 これにより、モバイルでのOutlookされます。

ポリシーの設定時にExchange Onlineおよび Outlookをポリシーのスコープに含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成する必要があります。 次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれているか確認します。 各ポリシーは、共通 ID およびデバイス アクセス ポリシーの関連する [構成手順にリンクします](identity-access-policies.md)。

|保護レベル|ポリシー|詳細情報|
|---|---|---|
|**開始点**|[サインインのリスクが *中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド Exchange Online割り当てにアプリを含める|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド Exchange Online割り当てにアプリを含める|
||[アプリ データ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|アプリのOutlookに含まれている必要があります。 各プラットフォームのポリシーを必ず更新してください (iOS、Android、Windows)|
||[承認済みアプリと APP 保護を要求する](identity-access-policies.md#require-approved-apps-and-app-protection)|クラウド Exchange Onlineリストにアプリを含める|
||[ActiveSync クライアントのブロック](#block-activesync-clients)|この新しいポリシーを追加する|
|**エンタープライズ**|[サインインのリスクが *低*、*中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド Exchange Online割り当てにアプリを含める|
||[準拠した PC *と* モバイル デバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド Exchange Onlineリストにアプリを含める|
|**特殊なセキュリティ**|[*常に* MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド Exchange Online割り当てにアプリを含める|
|

## <a name="block-activesync-clients"></a>ActiveSync クライアントのブロック

Exchange ActiveSyncデスクトップおよびモバイル デバイス上のメッセージングと予定表データの同期に使用できます。

モバイル デバイスの場合、Intune アプリ保護ポリシーをサポートしていない最新の認証対応の Exchange ActiveSync クライアント (またはアプリ保護ポリシーで定義されていないサポートされているクライアント) および基本認証を使用する Exchange ActiveSync クライアントは、[承認済みアプリと[アプリ](identity-access-policies.md#require-approved-apps-and-app-protection)保護を要求する] で作成された条件付きアクセス ポリシーに基づいてブロックされます。

他のデバイスExchange ActiveSync基本認証を使用して認証をブロックするには、「すべてのデバイスで [Exchange ActiveSync](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#block-exchange-activesync-on-all-devices) をブロックする」の手順に従って、Exchange ActiveSync クライアントがモバイル 以外のデバイスで基本認証を使用して接続を妨げるExchange Online。

また、認証ポリシーを使用して基本[](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)認証を無効にし、すべてのクライアント アクセス要求で最新の認証を使用できます。

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>ユーザーからのアクセスをExchange Online制限Outlook on the web

ユーザーが管理されていないデバイスから添付ファイルをダウンロードOutlook on the web制限できます。 これらのデバイス上のユーザーは、デバイスにファイルを漏洩して保存することなく、Office Online を使用してこれらのファイルを表示および編集できます。 ユーザーが管理されていないデバイスで添付ファイルを見るのをブロックすることもできます。

それらのステップは次のとおりです。

1. [Connect PowerShell セッションExchange Onlineにアクセスします](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。
2. OWA メールボックス ポリシーをまだ持ってない場合は、 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して作成します。
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

   **割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**Include** \>**アプリの選択**: [アプリの **選択Office 365 Exchange Online**

   **アクセス制御** \>**セッション**: [アプリ **の適用制限を使用する] を選択します。**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>iOS デバイスと Android デバイスでデバイスを使用する必要Outlook

iOS および Android デバイスのユーザーが、iOS および Android 用 Outlook を使用して仕事または学校のコンテンツにのみアクセスするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。

このポリシーを構成する手順については、「iOS および Android 用のメッセージング コラボレーション アクセスを使用してメッセージング Outlook[を管理する」を参照してください](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)。

## <a name="set-up-message-encryption"></a>メッセージの暗号化を設定する

Azure Information Protection のOffice 365 Message Encryption機能を活用する新しい OME (OME) 機能を使用すると、組織は保護された電子メールを任意のデバイスの誰とでも簡単に共有できます。 ユーザーは、Outlook.com、Gmail、その他の電子メール サービスを使用して、Microsoft 365組織や非顧客と保護されたメッセージを送受信できます。

詳細については、「Set [up new Office 365 Message Encryption」を参照してください](../../compliance/set-up-new-message-encryption-capabilities.md)。

## <a name="next-steps"></a>次の手順

![手順 4: Microsoft 365 クラウド アプリのポリシー。](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセス ポリシーを構成する:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
