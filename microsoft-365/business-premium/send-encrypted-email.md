---
title: 暗号化された電子メールを送信する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlookを使用して暗号化された電子メールを送信する方法について説明します。
ms.openlocfilehash: 9cf39d3147b5ef7a099a06737316ee20e6154775
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64946904"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>機密情報を暗号化またはラベル付けする

データとキャンペーンの情報は重要であり、多くの場合は機密です。 暗号化ラベルと秘密度ラベルを使用してこの機密情報を保護し、ユーザーと電子メール受信者が必要な秘密度で情報を処理できるようにします。

## <a name="best-practices"></a>ベスト プラクティス

機密情報または機密情報を含む電子メールを送信する前に、次の機能をオンにすることを検討してください。

- **暗号化：** 電子メールを暗号化して、電子メール内の情報のプライバシーを保護できます。 電子メール メッセージを暗号化すると、読み取り可能なプレーンテキストから暗号化されたサイファー テキストに変換されます。 メッセージの暗号化に使用される公開キーと一致する秘密キーを持つ受信者のみが、読み取り用にメッセージを解読できます。 ただし、対応する秘密キーを持たない受信者には、解読できないテキストが表示されます。 管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。 たとえば、管理者は、組織外で送信されたすべてのメッセージや、特定の単語やフレーズを言及するすべてのメッセージを暗号化するルールを作成できます。 暗号化規則は自動的に適用されます。
- **秘密度ラベル:** また、キャンペーンでは、ファイルやメールに適用できる秘密度ラベルを設定して、キャンペーンの情報保護ポリシーに準拠させることができます。 ラベルを設定すると、メッセージにヘッダーとして表示するなどして、ラベルが送信された場合でも、ラベルは電子メールと共に保持されます。

![ラベルと暗号化用の吹き出しを含む電子メールの図。](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>設定する

定義済みのルールを満たしていないメッセージを暗号化する場合、または管理者がルールを設定していない場合は、メッセージを送信する前にさまざまな暗号化規則を適用できます。 Outlook 2013 または 2016、またはOutlook 2016 for Macから暗号化されたメッセージを送信するには、[**オプション] > [アクセス許可**] を選択し、必要な保護オプションを選択します。 Outlook on the webの [**保護**] ボタンを選択して、暗号化されたメッセージを送信することもできます。 詳細については、「[PC 版 Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="admin-settings"></a>管理設定

Microsoft 365の電子メール暗号化で[電子メール暗号化](../compliance/email-encryption.md)を設定する方法について説明します。

### <a name="automatically-encrypt-email-messages"></a>電子メール メッセージを自動的に暗号化する

管理者は、キャンペーンから送受信されるメール メッセージを自動的に保護するメール フロー ルールを作成できます。 送信電子メール メッセージを暗号化し、組織内から送信された暗号化されたメッセージまたは組織内から送信された暗号化されたメッセージへの返信から暗号化を削除するルールを設定します。

Microsoft Purview メッセージ暗号化を使用して電子メール メッセージを暗号化するメール フロー ルールを作成します。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター (EAC)</a> を使用して、メッセージ暗号化をトリガーするためのメール フロー ルールを定義します。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校アカウントを使用してサインインします。
2. [管理者] タイルを選択します。
3. 管理センターで、[**管理センターの> Exchange**] を選択します。

詳細については、「 [メール メッセージを暗号化するメール フロー ルールを定義する」を](../compliance/define-mail-flow-rules-to-encrypt-email.md)参照してください。

### <a name="brand-your-encryption-messages"></a>暗号化メッセージをブランド化する

また、キャンペーン のブランドを適用して、メール メッセージの外観とテキストをカスタマイズすることもできます。 詳細については、「 [暗号化されたメッセージに組織のブランドを追加する」を参照してください](../compliance/email-encryption.md)。