---
title: セキュリティで保護された電子メール推奨ポリシー - Microsoft 365 for enterprise |Microsoft Docs
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
- zerotrust-solution
- highpri
ms.technology: mdo
ms.openlocfilehash: 4a63855d25a7ace428fd3fd93e134f4a6ffcbce3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482871"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

この記事では、モダン認証と条件付きアクセスをサポートする組織の電子メール クライアントと電子メール クライアントを保護するために推奨されるゼロ トラスト ID とデバイス アクセス ポリシーを実装する方法について説明します。 このガイダンスは [、共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md) に基づいて作成され、いくつかの追加の推奨事項も含まれています。

これらの推奨事項は、ニーズの粒度 ( **開始点**、 **エンタープライズ**、 **特殊な** セキュリティ) に基づいて適用できる 3 つのセキュリティと保護のレベルに基づいています。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、モバイル デバイス上の Outlook for iOS や Android など、ユーザーが最新の電子メール クライアントを使用する必要があります。 Outlook for iOS と Android は、Office 365の最適な機能をサポートします。 これらのモバイル Outlook アプリは、モバイル使用をサポートし、他の Microsoft クラウド セキュリティ機能と連携するセキュリティ機能も備えています。 詳細については、「 [Outlook for iOS と Android の FAQ](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)」を参照してください。

## <a name="update-common-policies-to-include-email"></a>一般的なポリシーを更新してメールを含める

電子メールを保護するために、次の図は、共通 ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png" alt-text="Microsoft Exchange へのアクセスを保護するためのポリシー更新プログラムの概要" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png":::

ActiveSync クライアントをブロックするためのExchange Onlineの新しいポリシーの追加に注意してください。 これにより、Outlook モバイルが強制的に使用されます。

ポリシーの設定時にポリシーのスコープにExchange Onlineと Outlook を含める場合は、ActiveSync クライアントをブロックする新しいポリシーを作成するだけで済みます。 次の表に示すポリシーを確認し、推奨される追加を行うか、既に含まれていることを確認します。 各ポリシーは、 [共通 ID ポリシーとデバイス アクセス ポリシー](identity-access-policies.md)の関連する構成手順にリンクします。

|保護レベル|ポリシー|詳細情報|
|---|---|---|
|**開始点**|[サインインのリスクが *中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てにExchange Onlineを含める|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|クラウド アプリの割り当てにExchange Onlineを含める|
||[アプリ データ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|Outlook がアプリの一覧に含まれていることを確認します。 プラットフォーム (iOS、Android、Windows) ごとにポリシーを必ず更新してください|
||[承認されたアプリと APP 保護を要求する](identity-access-policies.md#require-approved-apps-and-app-protection)|クラウド アプリの一覧にExchange Onlineを含める|
||[ActiveSync クライアントをブロックする](#block-activesync-clients)|この新しいポリシーを追加する|
|**エンタープライズ**|[サインインのリスクが *低*、*中*、または *高* のときに MFA を要求する](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てにExchange Onlineを含める|
||[準拠した PC *と* モバイル デバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウド アプリの一覧にExchange Onlineを含める|
|**特殊なセキュリティ**|[*常に* MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウド アプリの割り当てにExchange Onlineを含める|

## <a name="block-activesync-clients"></a>ActiveSync クライアントをブロックする

Exchange ActiveSyncを使用して、デスクトップデバイスとモバイル デバイス上のメッセージングデータと予定表データを同期できます。

モバイル デバイスの場合、Intuneアプリ保護ポリシー (またはアプリ保護ポリシーで定義されていないサポートされているクライアント) をサポートしていない先進認証対応のExchange ActiveSync クライアントと、基本認証を使用するExchange ActiveSyncクライアントは、作成された条件付きアクセス ポリシー[に基づいてブロックされます。承認されたアプリと APP 保護が必要](identity-access-policies.md#require-approved-apps-and-app-protection)です。

他のデバイスで基本認証を使用してExchange ActiveSyncをブロックするには、「[すべてのデバイスでExchange ActiveSyncをブロック](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#block-exchange-activesync-on-all-devices)する」の手順に従います。これにより、モバイル 以外のデバイスで基本認証を使用するExchange ActiveSyncクライアントが接続できなくなります。Exchange Online。

認証ポリシーを使用して [Basic 認証を無効に](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)することもできます。これにより、すべてのクライアント アクセス要求で先進認証が強制的に使用されます。

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Outlook on the webからのExchange Onlineへのアクセスを制限する

ユーザーがアンマネージド デバイス上のOutlook on the webから添付ファイルをダウンロードする機能を制限できます。 これらのデバイス上のユーザーは、デバイスにファイルを漏らしたり保存したりすることなく、Office Online を使用してこれらのファイルを表示および編集できます。 また、ユーザーがアンマネージド デバイスに添付ファイルを表示できないようにブロックすることもできます。

それらのステップは次のとおりです。

1. [Exchange Online PowerShell に接続します](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。
2. OWA メールボックス ポリシーがまだない場合は、 [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して作成します。
3. 添付ファイルの表示を許可するがダウンロードを許可しない場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. 添付ファイルをブロックする場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Azure portalで、次の設定を使用して新しい条件付きアクセス ポリシーを作成します。

   **割り当て** \>**ユーザーとグループ**: 含めるユーザーと除外する適切なユーザーとグループを選択します。

   **割り当て** \>**クラウド アプリまたはアクション** \>**クラウド アプリ** \>**含める** \>**アプリの選択**: **Office 365 Exchange Online** を選択する

   **アクセス制御** \>**セッション**: [**アプリの強制制限を使用** する] を選択します

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>iOS デバイスと Android デバイスで Outlook を使用する必要がある

iOS および Android デバイスのユーザーが Outlook for iOS と Android を使用して職場または学校のコンテンツにのみアクセスできるようにするには、それらの潜在的なユーザーを対象とする条件付きアクセス ポリシーが必要です。

このポリシーを構成する手順については、「 [Outlook for iOS と Android を使用したメッセージング コラボレーション アクセスの管理」を](/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)参照してください。

## <a name="set-up-message-encryption"></a>メッセージ暗号化を設定する

Azure Information Protectionの保護機能を利用するMicrosoft Purview Message Encryptionを使用すると、組織は保護された電子メールを任意のデバイス上の誰とでも簡単に共有できます。 ユーザーは、Outlook.com、Gmail、その他の電子メール サービスを使用して、他の Microsoft 365 組織や非顧客と保護されたメッセージを送受信できます。

詳細については、「[新しいOffice 365メッセージ暗号化機能の設定](../../compliance/set-up-new-message-encryption-capabilities.md)」を参照してください。

## <a name="next-steps"></a>次の手順

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Microsoft 365 クラウド アプリのポリシー" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

次の条件付きアクセス ポリシーを構成する:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
