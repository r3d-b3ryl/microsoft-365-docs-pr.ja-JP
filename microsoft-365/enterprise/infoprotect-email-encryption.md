---
title: '手順 6: 電子メールの暗号化を構成する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365 の特権アクセス管理について理解して構成します。
ms.openlocfilehash: 252a5f76197deb1034d200553308a281ef079957
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600924"
---
# <a name="step-6-configure-email-encryption"></a>手順 6: 電子メールの暗号化を構成する

*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

![フェーズ 6: 情報保護](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Microsoft 365 には、3種類の電子メール暗号化があります。

|||
|:-------|:-----|
| Office のメッセージ暗号化 (OME) | 組織外で送信された Exchange Online 電子メールの暗号化。 |
| Information Rights Management (IRM) | 電子メールと共に移動する暗号化とアクセス許可。 |
| Secure/Multipurpose Internet Mail Extensions (S/MIME) | 暗号化とデジタル署名による電子メール保護。 |
|||

## <a name="office-365-message-encryption"></a>はい

OME を使用すると、組織は組織内外のユーザー間で暗号化された電子メールメッセージの送受信を行うことができます。 OME は、Outlook.com、Yahoo!、Gmail、その他の電子メールサービスと連携して動作します。 電子メールメッセージの暗号化を使用すると、意図した受信者のみがメッセージを表示できるようになります。

![電子メールメッセージの OME 暗号化](./media/infoprotect-email-encryption/ome-encryption.png)

暗号化の条件を定義するトランスポートルールを設定します。 ユーザーがルールに一致するメッセージを送信する場合、自動的に暗号化が適用されます。

暗号化されたメッセージを表示するには、受信者はワンタイムパスコードを取得するか、Microsoft アカウントでサインインするか、Microsoft 365 に関連付けられた職場または学校のアカウントでサインインすることができます。 受信者は暗号化された返事を送信することもできます。 暗号化されたメッセージを表示したり、暗号化された返信を送信したりするために、独自の Microsoft 365 サブスクリプションは必要ありません。

詳細については、「 [Office 365 での暗号化](https://docs.microsoft.com/Office365/SecurityCompliance/ome)」を参照してください。

## <a name="irm"></a>IRM

Microsoft 365 の IRM は、追加の暗号化を使用して情報を保護し、ユーザーが実行できる操作を指定するインテリジェントポリシーを適用することにより、情報を保護します。 電子メールメッセージの場合は、暗号化に IRM を使用し、使用制限を適用することができます。 たとえば、一部の受信者がすべての電子メールを管理する機能を持ち、一部の受信者が電子メールを印刷または転送できないように指定することができます。 

IRM ポリシーは、Microsoft 365 内で構成されており、SharePoint Online および電子メールメッセージ内のドキュメントに適用できます。 IRM で保護された電子メールには、適用されたポリシー設定が含まれており、それと一緒に移動します。 

![電子メールメッセージの IRM 保護](./media/infoprotect-email-encryption/irm-protection.png)

受信者が含まれているポリシーを使用して電子メールを開くと、ポリシー設定を使用して、メッセージを復号化し、受信者が実行できる処理を決定します。 

詳細については、「 [Exchange Online での Information Rights Management]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online)」を参照してください。

## <a name="smime"></a>S/MIME

S/MIME は、デジタル証明書ベースの電子メールベースの保護ソリューションで、メッセージの暗号化とデジタル署名の両方を行うことができます。 メッセージを暗号化することで、本来の受信者だけがメッセージを開き、閲覧できます。 デジタル署名は、受信者が送信者の身元を確認し、送信者のみが送信したことを確認するのに便利です。

![電子メールメッセージの S/MIME 保護](./media/infoprotect-email-encryption/smime-protection.png)

S/MIME は、Microsoft 365 サブスクリプションの他のメールボックスまたは外部ユーザーに電子メールで使用できます。
メッセージ暗号化とデジタル署名の両方は、メッセージの暗号化または復号化、およびデジタル署名の作成と検証のための公開キーと秘密キーを含むデジタル証明書を使用することによって可能になります。
S/MIME を使用するには、各受信者の公開キーを持っている必要があります。 受信者は、自分の秘密キーを保持します。これは安全なままにする必要があります。 秘密キーが侵害された場合は、新しいデジタル証明書を取得して、公開キーをすべての潜在的な送信者に再配布する必要があります。

詳細については、「[S/MIME によるメッセージの署名と暗号化](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)」を参照してください。


中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 7](./media/stepnumbers/Step7.png)|[Office 365 の特権アクセス管理を構成する](infoprotect-configure-privileged-access-management.md)|
