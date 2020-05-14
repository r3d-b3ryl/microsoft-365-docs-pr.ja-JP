---
title: セキュリティで保護された電子メールの推奨されるポリシー - Microsoft 365 Enterprise | Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: e469f0d1c0be85aeb5f98a4f2e6e2758cddd8450
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222699"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

この記事では、推奨される id とデバイスアクセスポリシーを実装して、先進認証および条件付きアクセスをサポートする組織の電子メールと電子メールクライアントを保護する方法について説明します。 このガイダンスは、[一般的な id とデバイスのアクセスポリシー](identity-access-policies.md)を基に作成されており、さらにいくつかの推奨事項も含まれています。

これらの推奨事項は、ニーズの粒度 (**基準**、**機密**、**高規制**) に基づいて適用できる、セキュリティと保護の3つの異なる層に基づいています。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、ユーザーがモバイルデバイスの iOS および Android 用の Outlook を含むモダンメールクライアントを使用する必要があります。 IOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。 これらのモバイル Outlook アプリは、モバイル使用をサポートし、他の Microsoft クラウドセキュリティ機能と連携するセキュリティ機能を備えた設計も行われています。 詳細については、「 [iOS および Android 用の OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)」を参照してください。

## <a name="updating-common-policies-to-include-email"></a>電子メールを含めるための共通ポリシーの更新

次の図は、一般的な id およびデバイスアクセスポリシーを示し、電子メールを保護するために更新する必要があるポリシーを示しています。 ActiveSync クライアントをブロックする Exchange Online の新しいルールの追加に注意してください。 これにより、Outlook mobile が強制的に使用されます。

![メールを保護するためのポリシー更新の概要](../media/identity-access-ruleset-mail.png)

ポリシーの設定時に Exchange Online と Outlook がポリシーのスコープに含まれていた場合は、ActiveSync クライアントをブロックするために新しいポリシーを作成するだけでよいことになります。 次の表に記載されているポリシーを確認し、推奨される追加を行うか、またはこれらが既に含まれていることを確認します。 各ルールは、[一般的な id およびデバイスアクセスポリシー](identity-access-policies.md)の記事に記載されている関連する構成手順にリンクします。

|保護レベル|ポリシー|More information|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|
|        |[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウドアプリの割り当てに Exchange Online を含める|
|        |[アプリデータ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|Outlook がアプリの一覧に含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。|
|        |[承認済みアプリとアプリ保護を必要とする](identity-access-policies.md#require-approved-apps-and-app-protection)|クラウドアプリの一覧に Exchange Online を含める|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウドアプリの一覧に Exchange Online を含める|
|        |[ActiveSync クライアントをブロックする](#block-activesync-clients)|この新しいポリシーを追加する| 
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| クラウドアプリの割り当てに Exchange Online を含める|
|         |[準拠*して*いる pc とモバイルデバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウドアプリの一覧に Exchange Online を含める|
|**高度な規制**|[*常に*MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|

## <a name="block-activesync-clients"></a>ActiveSync クライアントをブロックする

このポリシーでは、ActiveSync クライアントが他の条件付きアクセスルールをバイパスできないようにします。 ルール構成は、ActiveSync クライアントにのみ適用されます。 [**[アプリ保護ポリシーを必須](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** にする] を選択すると、このポリシーによって ActiveSync クライアントがブロックされます。 このポリシーの作成の詳細については、「[条件付きアクセスでのクラウドアプリケーションへのアクセスにアプリ保護ポリシーが必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)」を参照してください。

1. 「[シナリオ 1: Office 365 アプリは、アプリ保護ポリシーを使用して承認済みアプリを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)とする」の「手順 2: exchange Online の Azure AD 条件付きアクセスポリシーを構成する」を参照してください。これにより、exchange ActiveSync クライアントは、基本認証を活用して exchange online に接続することができなくなります。

## <a name="set-up-message-encryption"></a>メッセージの暗号化をセットアップする

新しい Office 365 Message Encryption (OME) 機能を使用すると、Azure Information Protection の保護機能を活用できるため、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと簡単に共有できます。 ユーザーは、保護されたメッセージを他の Microsoft 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用しないお客様との間で送受信することができます。

詳細については、「 [Office の新しい365メッセージ暗号化機能をセットアップ](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)する」を参照してください。

## <a name="next-steps"></a>次の手順

[SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項の詳細](sharepoint-file-access-policies.md)
