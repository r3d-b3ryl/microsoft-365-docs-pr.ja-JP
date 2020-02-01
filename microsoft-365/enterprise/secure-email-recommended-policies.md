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
ms.openlocfilehash: e8c2b10f3e1dd88703b15c326dedb164a686cfca
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596734"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

この記事では、推奨される id とデバイスアクセスポリシーを実装して、先進認証および条件付きアクセスをサポートする組織の電子メールと電子メールクライアントを保護する方法について説明します。 このガイダンスは、[一般的な id とデバイスのアクセスポリシー](identity-access-policies.md)を基に作成されており、さらにいくつかの推奨事項も含まれています。

これらの推奨事項は、ニーズの粒度 (**基準**、**機密**、**高規制**) に基づいて適用できる、セキュリティと保護の3つの異なる層に基づいています。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、ユーザーがモバイルデバイスの iOS および Android 用の Outlook を含むモダンメールクライアントを使用する必要があります。 IOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。 これらのモバイル Outlook アプリは、モバイル使用をサポートし、他の Microsoft クラウドセキュリティ機能と連携するセキュリティ機能を備えた設計も行われています。 詳細については、「 [iOS および Android 用の OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)」を参照してください。

## <a name="updating-common-policies-to-include-email"></a>電子メールを含めるための共通ポリシーの更新

次の図は、一般的な id およびデバイスアクセスポリシーを示し、電子メールを保護するために更新する必要があるポリシーを示しています。 ActiveSync クライアントをブロックする Exchange Online の新しいルールの追加に注意してください。 これにより、Outlook mobile が強制的に使用されます。

![メールを保護するためのポリシー更新の概要](../images/identity-access-ruleset-mail.png)

ポリシーの設定時に Exchange Online と Outlook がポリシーのスコープに含まれていた場合は、ActiveSync クライアントをブロックするために新しいポリシーを作成するだけでよいことになります。 次の表に記載されているポリシーを確認し、推奨される追加を行うか、またはこれらが既に含まれていることを確認します。 各ルールは、[一般的な id およびデバイスアクセスポリシー](identity-access-policies.md)の記事に記載されている関連する構成手順にリンクします。

|保護レベル|ポリシー|詳細情報|
|:---------------|:-------|:----------------|
|**Baseline**|[サインインリスクが*中*または*高*の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|
|        |[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウドアプリの割り当てに Exchange Online を含める|
|        |[アプリ保護ポリシーを定義する](identity-access-policies.md#high-risk-users-must-change-password)|Outlook がアプリの一覧に含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。|
|        |[承認済みアプリの要求](identity-access-policies.md#require-approved-apps)|クラウドアプリの一覧に Exchange Online を含める|
|        |[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウドアプリの一覧に Exchange Online を含める|
|        |[ActiveSync クライアントをブロックする](#block-activesync-clients)|この新しいポリシーを追加する| 
|**機密**|[サインインリスクが*低*、*中*、*高*のときに MFA を必要とする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| クラウドアプリの割り当てに Exchange Online を含める|
|         |[準拠*して*いる pc とモバイルデバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウドアプリの一覧に Exchange Online を含める|
|**厳しく規制**|[*常に*MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|

## <a name="block-activesync-clients"></a>ActiveSync クライアントをブロックする

このポリシーでは、ActiveSync クライアントが他の条件付きアクセスルールをバイパスできないようにします。 ルール構成は、ActiveSync クライアントにのみ適用されます。 [承認された**クライアントアプリを必要と**する] を選択すると、このポリシーは ActiveSync クライアントをブロックします。 このポリシーを構成するには

1. [Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。 サインインに成功すると、Azure ダッシュボードが表示されます。

2. 左側のメニューから **[Azure Active Directory]** を選びます。

3. **[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。

4. **[新しいポリシー]** を選びます。

5. ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。

6. **[クラウド アプリ]** を選びます。

7. **[アプリの選択**] を選択し、[ **Office 365 Exchange Online**] を選択します。 **[選択**して**完了**] を選択します。

8. [**条件**] を選択してから、[**クライアントアプリ**] を選択します。

9. [**構成**] で、[**はい]** を選択します。 [**モバイルアプリ] と [デスクトップクライアント**] および [ **Exchange ActiveSync クライアント**] のみをチェックします。 [ **Done**] を選びます。

10. **[アクセス制御]** セクションから **[許可]** を選びます。

11. [**アクセス許可の付与**] を選択し、[**承認済みクライアントアプリの要求**] を選択します。  複数のコントロールの場合は、[選択した**コントロールを必要とする**] を選択し、[**選択**] を選択します。

12. [**作成**] を選択します。

## <a name="setup-office-365-message-encryption"></a>Office 365 メッセージの暗号化のセットアップ

新しい Office 365 Message Encryption (OME) 機能を使用すると、Azure Information Protection の保護機能を活用できるため、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと簡単に共有できます。 ユーザーは、Outlook.com、Gmail、その他の電子メールサービスを使用して、他の Office 365 組織および非 Office 365 ユーザーとの保護されたメッセージを送受信できます。

詳細については、「 [Office の新しい365メッセージ暗号化機能をセットアップ](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e)する」を参照してください。

## <a name="next-steps"></a>次の手順

[SharePoint サイトおよびファイルをセキュリティで保護するためのポリシーの推奨事項の詳細](sharepoint-file-access-policies.md)
