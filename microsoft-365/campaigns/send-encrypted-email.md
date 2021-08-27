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
description: 電子メールを使用して暗号化された電子メールを送信するOutlook。
ms.openlocfilehash: 789477557801f2c8b89fa2bb281d0b0f2faf993a
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58567110"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>機密情報を暗号化またはラベル付けする

データとキャンペーン情報は重要であり、多くの場合、機密です。 暗号化ラベルと機密ラベルを使用してこの機密情報を保護し、ユーザーと電子メール受信者が必要な機密性で情報を処理します。

## <a name="best-practices"></a>ベスト プラクティス

機密情報または機密情報を含む電子メールを送信する前に、次の機能をオンにしてください。

- **暗号化:** 電子メールを暗号化して、電子メール内の情報のプライバシーを保護できます。 電子メール メッセージを暗号化すると、読み取り可能なプレーン テキストからスクランブルされたサイファー テキストに変換されます。 メッセージの暗号化に使用される公開キーと一致するプライベート キーを持つ受信者だけが、メッセージを読み取り用に解読できます。 ただし、対応するプライベート キーのない受信者には、解読できないテキストが表示されます。 管理者は、特定の条件を満たすメッセージを自動的に暗号化するルールを定義できます。 たとえば、管理者は、組織外で送信されたメッセージまたは特定の単語や語句に言及しているすべてのメッセージを暗号化するルールを作成できます。 暗号化ルールは自動的に適用されます。
- **感度ラベル:** また、キャンペーンでは、ファイルやメールに適用できる感度ラベルを設定して、キャンペーンの情報保護ポリシーに準拠することができます。 ラベルを設定すると、メッセージにヘッダーとして表示されるなど、送信された場合でも、ラベルはメールと一緒に保持されます。

![ラベルと暗号化の吹き出しを含む電子メールの図。](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>設定する

定義済みのルールを満たしないメッセージや管理者がルールを設定しないメッセージを暗号化する場合は、メッセージを送信する前にさまざまな暗号化ルールを適用できます。 Outlook 2013 または 2016、または Outlook 2016 for Mac から暗号化されたメッセージを送信するには、[オプション>**アクセス** 許可] を選択し、必要な保護オプションを選択します。 暗号化されたメッセージを送信するには、サーバーの [保護] ボタン **を選択** Outlook on the web。 詳細については、「[PC 版 Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="admin-settings"></a>管理設定

電子メール暗号化の設定については、「メール暗号化」の「Microsoft 365」[を参照してください](../compliance/email-encryption.md)。

### <a name="automatically-encrypt-email-messages"></a>電子メール メッセージを自動的に暗号化する

管理者はメール フロー ルールを作成して、キャンペーンから送信および受信される電子メール メッセージを自動的に保護できます。 送信電子メール メッセージを暗号化するルールを設定し、組織内から送信される暗号化されたメッセージ、または組織から送信された暗号化されたメッセージへの返信から暗号化を削除します。

メール フロー ルールを作成して、新しいメール メッセージ (OME) 機能Office 365 Message Encryptionメール メッセージを暗号化します。 新しい OME 機能を使用してメッセージ暗号化をトリガーするメール フロー ルールを定義するには、Exchange管理センター (EAC) を使用します。 

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている仕事または学校のアカウントを使用してサインインします。
2. [管理] タイルを選択します。
3. 管理センターで、[管理センター]**を選択> Exchange。**

詳細については、「メール メッセージを暗号化 [するメール フロー ルールを定義する」を参照してください](../compliance/define-mail-flow-rules-to-encrypt-email.md)。

### <a name="brand-your-encryption-messages"></a>暗号化メッセージのブランド化

また、キャンペーン のブランド化を適用して、電子メール メッセージの外観とテキストをカスタマイズすることもできます。 詳細については、「暗号化 [されたメッセージに組織のブランドを追加する」を参照してください](../compliance/email-encryption.md)。