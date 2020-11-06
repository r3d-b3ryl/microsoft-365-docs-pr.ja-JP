---
title: 違反の通知
description: Microsoft サービスによる個人データ漏洩からの保護と、違反が発生した場合の Microsoft による対応とユーザーへの通知について説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: a671fc9234f76c63ff7336369c87e680a4432cc3
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920291"
---
# <a name="gdpr-breach-notification"></a>GDPR 違反の通知

The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located. Additional details can be found in the [GDPR Summary topic](gdpr.md). This document leads you to information on the completion of Breach Notifications under the GDPR using Microsoft products and services.

## <a name="what-constitute-a-breach-of-personal-data-under-the-gdpr"></a>GDPR における個人データ侵害とは?

Personal data means any information related to an individual that can be used to identify them directly or indirectly. A personal data breach is 'a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorized disclosure of, or access to, personal data transmitted, stored, or otherwise processed'.

## <a name="terminology"></a>用語

このドキュメントで使用されている GDPR 用語の役に立つ定義:

- *データ コントローラー (コントローラー)* : 法人、公的機関、団体、その他の組織。単独または他者と協力して、個人データの処理の目的と方法を決定します。  
- *個人データ* と *データ主体* : 特定されたまたは特定可能な自然人 (データ主体) に関連するあらゆる情報。特定可能な自然人とは、直接または間接的に特定することができる者のことです。  
- *処理者* : コントローラーに代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。  
- *顧客データ* : ビジネス運営における日々の業務で作成および保存されるデータ。

## <a name="microsoft-and-breach-notification"></a>Microsoft と違反の通知

Microsoft takes its obligations under the General Data Protection Regulation (GDPR) seriously. A security incident/data breach refers to events such as unlawful access to customer's data stored on Microsoft equipment or in Microsoft facilities, or unauthorized access to such that has the potential to result in the loss, disclosure, or alteration of customer data.

As a data processor, Microsoft ensures that service customers are able to meet the GDPR's breach notification requirements as data controllers. Our notification provides the information needed to make that assessment. Microsoft notifies customers of any personal data breach, except for those cases where personal data is confirmed to be unintelligible (for example, encrypted data where integrity of the keys is confirmed).

Data controllers are responsible for assessing risks to data privacy and determining whether a breach requires notification of a customer's DPA. Microsoft provides the information needed, along with your GDPR compliance policy, to make that assessment.

Initial notification includes a description of the nature of the breach, approximate user impact, and mitigation steps (if applicable). If our investigation is not complete at the time of initial notification, we will indicate next steps and timelines for subsequent communication. For more information about how Microsoft detects and responds to a breach of personal data, see [Data Breach Notification Under the GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) in the Service Trust Portal.

特定の Microsoft 製品およびサービスに関する侵害の通知の詳細は、以下の通りです。
  
1. **[Office 365](gdpr-breach-Office365.md)**  
    Microsoft invests extensively in systems, processes, and personnel to reduce the likelihood of personal data breach and to quickly detect and mitigate consequence of breach if it does occur. Additional details can be read at [Office 365 Investments in Data Security](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-office365#office-365-investments-in-data-security).

    A customer may become aware of a breach and wish to contact Microsoft. In this case, notify Microsoft Support, which will then interface with engineering teams for more information.

2. **[Azure および Dynamics 365](gdpr-breach-azure-dynamics.md)**  
    Microsoft には、Microsoft Azure および Dynamics 365 に対する攻撃の影響緩和を目的とした、24 時間 365 日体制のインシデント対応サービスがあります。

    - *Detection of Breaches* : Since both Microsoft and the customer have security obligations, Azure services employ a shared responsibility model to define security and operational accountabilities. Microsoft does not monitor or respond to security incidents within the customer's realm of responsibility. Customer incident response may involve collaboration with Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. Microsoft Azure also offers various services (for example, [Azure Defender](https://azure.microsoft.com/services/security-center/)) that customers can utilize for developing and managing security incident response.

        For a list of events that trigger a breach investigation in Microsoft Azure, see [Detection of Potential Breaches](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#detection-of-potential-breaches). [Azure and Breach Notification under the GDPR](gdpr-breach-azure-dynamics.md) further details how Microsoft investigates, manages, and responds to security incidents within Azure.

    - *Data Breach Response* : Microsoft determines appropriate priority and severity levels of a breach by investigating the functional impact, recoverability, and information impact of the incident. Priority and severity may change over the course of the investigation, based on new findings and conclusions. Microsoft's security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. These processes are detailed in [Azure's Data Breach Response](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#azures-data-breach-response).

    - *Customer Notification* : Microsoft Azure notifies customers and regulatory authorities of data breaches as required. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances:

        - Microsoft が、通知を実行すると他のユーザーにとってリスクが増大する判断した場合。
        - The 72-hour timeline may leave some incident details available. These details will be provided to you as the investigation proceeds.

        詳細については、「[お客様への通知](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-azure-dynamics#customer-notification)」を参照してください。

3. **[Microsoft サポート/プロフェッショナル サービス](gdpr-breach-Microsoft-Support-Professional-Services.md)**  
    The nature of professional services means that some data protection incidents may fall within the customer's realm of responsibility. When Microsoft Professional Services identifies a data protection incident, it follows documented industry standard response plan as outlined in [Scope & Limits of Data Protection Incident Response Process](https://docs.microsoft.com/microsoft-365/compliance/gdpr-breach-microsoft-support-professional-services#scope--limits-of-data-protection-incident-response-process).

## <a name="breach-notification-admin-tools"></a>違反の通知管理ツール

- **組織のプライバシー連絡先の設定** : テナント管理者は [Azure Active Directory 管理ポータル](https://go.microsoft.com/fwlink/p/?linkid=2052736)を使用して、Microsoft が連絡を取る必要がある組織のプライバシー連絡先を定義できます。

## <a name="learn-more"></a>詳細情報

- [Microsoft Trust Center](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
