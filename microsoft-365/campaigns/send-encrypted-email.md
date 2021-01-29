---
title: 暗号化された電子メールを送信する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook を使用して暗号化された電子メールを送信する方法について学習します。
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044218"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>機密情報を暗号化またはラベル付けする

データとキャンペーン情報は重要であり、多くの場合は機密です。 暗号化ラベルと機密ラベルを使用してこの機密情報を保護し、ユーザーと電子メールの受信者が必要な機密で情報を扱うのに役立ちます。

## <a name="best-practices"></a>ベスト プラクティス

機密情報または機密情報を含むメールを送信する前に、次の機能をオンにしてください。

- **暗号化:** 電子メールを暗号化して、メール内の情報のプライバシーを保護できます。 電子メール メッセージを暗号化すると、読み取り可能なプレーン テキストからスcrambled cypher テキストに変換されます。 メッセージの暗号化に使用された公開キーと一致する公開キーを持つ受信者だけが、メッセージを読み取りのために解読できます。 ただし、対応するプライベート キーを持つ受信者には、暗号化できないテキストが表示されます。 管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。 たとえば、管理者は、組織外に送信されたメッセージすべて、または特定の単語または語句をメンションしているすべてのメッセージを暗号化するルールを作成できます。 暗号化ルールは自動的に適用されます。
- **[Sensitivity labels] (感度ラベル):** キャンペーンでは、ファイルやメールに適用できるラベルを設定して、キャンペーンの情報保護ポリシーに準拠し続けることもできます。 ラベルを設定すると、ラベルは、たとえばメッセージのヘッダーとして表示されるなど、送信された場合でも、電子メールと一緒に保持されます。

![ラベルと暗号化の吹き出しを含む電子メールの図](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>設定する

定義済みのルールを満たしないメッセージを暗号化する場合や、管理者がルールを設定しない場合は、メッセージを送信する前にさまざまな暗号化ルールを適用できます。 Outlook 2013 または 2016、または Outlook 2016 for Mac から暗号化されたメッセージを送信するには、[オプション **] > [** アクセス許可] を選択し、必要な保護オプションを選択します。 Outlook on the web で [保護] ボタンを選択して、暗号化されたメッセージを送信することもできます。 詳細については、Outlook for PC での暗号化されたメッセージの送信、表示、および返信 [に関するページを参照してください](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。

## <a name="admin-settings"></a>管理設定

[Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)の電子メール暗号化でのメール暗号化の設定についてすべて学習できます。

### <a name="automatically-encrypt-email-messages"></a>電子メール メッセージを自動的に暗号化する

管理者は、メール フロー ルールを作成して、キャンペーンから送信および受信される電子メール メッセージを自動的に保護できます。 送信電子メール メッセージを暗号化するルールを設定し、組織内から送信される暗号化されたメッセージや、組織から送信された暗号化されたメッセージへの返信から暗号化を削除します。

新しい OME (Office Message Encryption) 機能を使用して電子メール メッセージを暗号化するメール フロー ルールを作成します。 Exchange 管理センター (EAC) を使用して、新しい OME 機能を使用してメッセージの暗号化をトリガーするメール フロー ルールを定義します。 

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている、仕事用または学校用のアカウントを使用してサインインします。
2. [管理者] タイルを選択します。
3. In the admin center, choose **Admin centers > Exchange**.

詳細については、「電子メール メッセージを [暗号化するメール フロー ルールの定義」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。

### <a name="brand-your-encryption-messages"></a>暗号化メッセージをブランド化する

キャンペーン のブランド化を適用して、メール メッセージの外観とテキストをカスタマイズすることもできます。 詳細については、「暗号化された [メッセージに組織のブランドを追加する」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。
