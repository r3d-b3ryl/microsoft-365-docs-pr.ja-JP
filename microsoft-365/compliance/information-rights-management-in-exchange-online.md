---
title: AD RMS による Exchange Online のメールの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: 社内の Active Directory Rights Management サービス (AD RMS) を使用して組織の要件を満たすように Exchange Online IRM を構成する方法について説明します。
ms.openlocfilehash: be53b54328c2c1e08e51a84b7251e23c3e7468c3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815444"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>AD RMS による Exchange Online のメールの暗号化

情報漏洩を防止するために、Exchange Online には、電子メール メッセージおよび添付ファイルをオンラインおよびオフラインで保護する Information Rights Management (IRM) 機能が搭載されています。 必要に応じて、社内の Active Directory Rights Management サービス (AD RMS) を使用するように Exchange Online IRM を構成し、組織の要件を満たすようにすることができます。 これは一般的ではありません。 AD RMS を使用するための要件がない場合は、代わりに[Office 365 メッセージの暗号化](ome.md)を使用します。 

IRM 保護は、ユーザーが Microsoft Outlook や Outlook on the web で適用したり、管理者がトランスポート保護ルールや Outlook の保護ルールを使用して適用したりできます。 IRM を使用すると、管理者とユーザーは、電子メールに含まれている機密性の高いデータのアクセス、転送、印刷、コピーをだれに許可するかを管理できるようになります。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>IRM と Office 365 Message Encryption (OME) および Azure Active Directory が協働する方法に関する変更点

As of September 2017, when you set up the new Office 365 Message Encryption capabilities for your organization, you also set up IRM for use with Azure Rights Management (Azure RMS). You no longer set up IRM with Azure RMS separately. Instead, OME and rights management work seamlessly together. For more details about the new capabilities, see [Office 365 Message Encryption FAQ](https://docs.microsoft.com/microsoft-365/compliance/ome-faq). If you're ready to get started using the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM が Exchange Online および Active Directory Rights Management サービスと協働する方法

Exchange Online IRM uses on-premises Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.
  
Users can apply a template to an email message to control the permissions that recipients have on a message. Actions, such as forwarding, extracting information from a message, saving a message or printing a message can be controlled by applying an AD RMS rights policy to the message.
  
Windows Server 2008 以降を実行している AD RMS サーバーを使用するよう IRM を構成できます。 この AD RMS サーバーは、クラウドベースの組織の AD RMS 権利ポリシー テンプレートを管理するために使用できます。 Outlook では、ユーザーが IRM 保護を送信メッセージに適用できるようにする目的にも AD RMS サーバーが使用されます。 詳細については、「[オンプレミスの AD RMS サーバーを使用するように IRM を構成する](configure-irm-to-use-an-on-premises-ad-rms-server.md)」を参照してください。 
  
有効になっていれば、次のように、IRM 保護をメッセージに適用できます。
  
- **Users can manually apply a template using Outlook and Outlook on the web.** Users can apply an AD RMS rights policy template to an email message by selecting the template from the **Set permissions** list. When users send an IRM-protected message, any attached files that use a supported format also receive the same IRM protection as the message. IRM protection is applied to files associated with Word, Excel, and PowerPoint, as well as .xps files and attached email messages. 
    
- **Administrators can use transport protection rules to apply IRM protection automatically to both Outlook and Outlook on the web.** You can create transport protection rules to IRM-protect messages. Configure the transport protection rule action to apply an AD RMS rights policy template to messages that meet the rule condition. After you enable IRM, your organization's AD RMS rights policy templates are available to use with the transport protection rule action called **Apply rights protection to the message with**.
    
- **Administrators can create Outlook protection rules.** Outlook protection rules automatically apply IRM-protection to messages in Outlook 2010 (not Outlook on the web) based on message conditions that include the sender's department, who the message is sent to, and whether recipients are inside or outside your organization. For details, see [Create an Outlook Protection Rule](https://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    

