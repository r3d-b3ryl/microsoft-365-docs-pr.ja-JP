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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Outlook を使用して暗号化された電子メールを送信する方法について説明します。
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322149"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>機密メールを暗号化またはラベル付けする

データおよびキャンペーン情報は重要であり、機密であることがよくあります。 暗号化と機密情報のラベルを使用してこの機密情報を保護すると、電子メールの受信者は、必要な機密度で情報を扱うことができます。


## <a name="best-practices"></a>ベスト プラクティス

機密情報または機密情報を含む電子メールを送信する前に、次のことを検討してください。

- **暗号化:** 電子メールを暗号化して、電子メール内の情報のプライバシーを保護することができます。 電子メールメッセージを暗号化すると、読み取り可能なプレーンテキストからスクランブル cypher テキストに変換されます。 メッセージの暗号化に使用された公開キーと一致する秘密キーを持つ受信者のみが、メッセージの読み取りのための解読を行うことができます。 ただし、対応する秘密キーを持たない受信者は、認識できないテキストを認識します。 管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。 たとえば、組織外から送信されたすべてのメッセージ、または特定の単語や語句を含むすべてのメッセージを暗号化するルールを作成できます。 暗号化ルールは自動的に適用されます。
- **機密ラベル:** キャンペーンでは、ファイルや電子メールに適用して、キャンペーンの情報保護ポリシーに準拠させることができる、機密ラベルを設定することもできます。 ラベルを設定すると、ラベルが送信された場合でも、メッセージのヘッダーとして表示されます。

![ラベルと暗号化の吹き出しが付いた電子メールの図](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>設定する

事前に定義されたルールに準拠していないメッセージを暗号化する場合、または管理者がルールを設定していない場合は、メッセージを送信する前にさまざまな暗号化ルールを適用できます。 暗号化されたメッセージを Outlook 2013 または2016、または Outlook 2016 for Mac から送信するには、[**オプション > のアクセス許可**] を選択し、必要な保護オプションを選択します。 また、暗号化されたメッセージを送信するには、Outlook on the web で [**保護**] をクリックします。 詳細については、「 [Outlook FOR PC での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="admin-settings"></a>管理設定

「 [Office 365 での](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)電子メールの暗号化による電子メールの暗号化の設定について」を参照してください。

### <a name="automatically-encrypt-email-messages"></a>電子メールメッセージを自動的に暗号化する

管理者は、メールフロールールを作成して、キャンペーンから送受信される電子メールメッセージを自動的に保護することができます。 送信電子メールメッセージを暗号化するルールを設定し、組織内から送信される暗号化されたメッセージ、または組織から送信された暗号化メッセージへの返信から暗号化を削除します。 

メールフロールールを作成して、新しい Office 365 Message Encryption (OME) 機能を使用して電子メールメッセージを暗号化します。 Exchange 管理センター (EAC) を使用して、新しい OME 機能でメッセージの暗号化をトリガーするためのメールフロールールを定義します。 

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、Office 365 にサインインします。 
2. [管理] タイルを選択します。 
3. 管理センターで、[ **Exchange > 管理センター**] を選択します。 

詳細については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)」を参照してください。

### <a name="brand-your-encryption-messages"></a>暗号化メッセージをブランド化する

また、キャンペーンブランドを適用して、電子メールメッセージの外観やテキストをカスタマイズすることもできます。 詳細については、「[組織のブランドを暗号化されたメッセージに追加する](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)」を参照してください。

