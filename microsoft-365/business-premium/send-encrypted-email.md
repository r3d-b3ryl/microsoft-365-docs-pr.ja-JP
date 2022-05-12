---
title: 暗号化された電子メールを送信する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 03/08/2022
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
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
description: Outlook を使用して暗号化されたメールを送信する方法について説明します。
ms.openlocfilehash: b9b2251114831bfe0b6364dc4327bd0c21da55e2
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316834"
---
# <a name="encrypt-or-label-sensitive-email"></a>機密情報を暗号化またはラベル付けする

データと情報は重要であり、多くの場合、機密です。ここでの目的は、すべてのユーザーが秘密度ラベルを使用し、メール受信者が最大限の秘密度で情報を扱うようにすることで、この機密情報を保護できるようにすることです。

## <a name="best-practices"></a>ベスト プラクティス

個人が機密情報または機密情報を含むメールを送信する前に、次の機能を有効にすることを検討する必要があります。

- **暗号化:** メールを暗号化して、メール内の情報のプライバシーを保護できます。 メール メッセージを暗号化すると、読み取り可能なプレーン テキストから暗号化されたサイファー テキストに変換されます。 メッセージの暗号化に使用される公開キーと一致する秘密キーを持つ受信者のみが、読み取り用にメッセージを解読できます。 ただし、対応する秘密キーを持たない受信者には、解読できないテキストが表示されます。 管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。 たとえば、管理者は、組織外で送信されたすべてのメッセージや、特定の単語やフレーズを言及するすべてのメッセージを暗号化するルールを作成できます。 暗号化規則は自動的に適用されます。

- **秘密度ラベル:** 組織で必要な場合は、ファイルとメールに適用する秘密度ラベルを設定して、組織の情報保護ポリシーに準拠させることができます。 ラベルを設定すると、たとえばメッセージのヘッダーとして表示されるなどして &mdash; が送信された場合でも、ラベルはメールに残ります。

![ラベルと暗号化のコールアウトを含むメールの図。](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>設定する

定義済みのルールを満たしていないメッセージを暗号化する場合、または管理者がルールを設定していない場合は、メッセージを送信する前にさまざまな暗号化規則を適用できます。 Outlook 2013 または 2016、または Outlook 2016 for Mac から暗号化されたメッセージを送信するには、**[オプション] > [アクセス権]** を選択し、必要な保護オプションを選択します。 Outlook on the web の [**保護**] ボタンを選択して、暗号化されたメッセージを送信することもできます。 詳細については、「[PC 版 Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="admin-settings"></a>管理設定

[[Microsoft 365 のメール暗号化]](../compliance/email-encryption.md) でメール暗号化を設定する方法について説明します。

### <a name="automatically-encrypt-email-messages"></a>メール メッセージを自動的に暗号化する

管理者は、キャンペーンまたはビジネスから送受信されるメール メッセージを自動的に保護するメール フロー ルールを作成できます。 送信メールメッセージを暗号化するルールを設定し、組織内からの暗号化メッセージまたは組織から送信された暗号化メッセージへの返信から暗号化を削除します。

Microsoft Purview メッセージ暗号化を使用して、メール メッセージを暗号化するメール フロー ルールを作成します。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター (EAC)</a> を使用して、メッセージ暗号化をトリガーするためのメール フロー ルールを定義します。

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校アカウントを使用してサインインします。
2. [管理者] タイルをクリックします。
3. 管理センター上で、**[管理センター] > [Exchange]** を選択します。

詳細については、「[メール メッセージを暗号化するためのメール フロー ルールを定義](../compliance/define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

### <a name="brand-your-encryption-messages"></a>暗号化メッセージをブランディングする

ブランディングを適用して、メール メッセージの外観とテキストをカスタマイズすることもできます。 詳細については、「[暗号化されたメッセージに組織のブランドを追加する](../compliance/email-encryption.md)」を参照してください。

## <a name="next-mission"></a>次のミッション

ここまで進んだということは、新しいミッション正常に完了したということです。おめでとうございます。 でも、成功に浸っている時間はありません。チームが[安全に共同作業](m365bp-collaborate-share-securely.md)できる安全な環境をすぐに設定しましょう。