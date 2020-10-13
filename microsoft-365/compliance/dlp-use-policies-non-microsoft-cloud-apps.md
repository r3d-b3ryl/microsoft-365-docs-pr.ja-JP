---
title: Microsoft 以外のクラウドアプリのデータ損失防止ポリシーを使用する (プレビュー)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 以外のクラウドアプリで dlp ポリシーを使用する方法について説明します。
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422759"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Microsoft 以外のクラウドアプリのデータ損失防止ポリシーを使用する (プレビュー)

Microsoft 以外のクラウドアプリに対するデータ損失防止 (DLP) ポリシーは、Microsoft 365 DLP スイートの機能の一部です。これらの機能を使用すると、Microsoft 365 サービス全体の機密アイテムを検出して保護することができます。 すべての Microsoft DLP オファーリングの詳細については、「 [データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)」を参照してください。

Microsoft 以外のクラウドアプリで DLP ポリシーを使用すると、機密性の高いアイテムが使用されているときを監視および検出したり、Microsoft 以外のクラウドアプリで共有したりすることができます。 これらのポリシーを使用すると、それらが適切に使用および保護されていることを確認するために必要な可視性と制御が提供されます。また、それらのポリシーを侵害する可能性のある動作を防ぐことができます。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

Microsoft 以外のクラウドアプリへの DLP ポリシーの使用を開始する前に、 [microsoft 365 のサブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) とアドオンを確認してください。 この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンを持っている必要があります。

- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>クラウドアプリのセキュリティ環境を準備する

Microsoft 以外のクラウドアプリへの DLP ポリシーは、Cloud App Security DLP 機能を使用します。 これを使用するには、Cloud App Security 環境を準備する必要があります。 手順については、「 [Set isntant visibility, protection, and ガバナンスの操作](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)」を参照してください。

### <a name="connect-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウドアプリを接続する

特定の Microsoft 以外のクラウドアプリに DLP ポリシーを使用するには、アプリが Cloud App Security に接続されている必要があります。 詳細については、次を参照してください。

- [[接続] ボックス](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [接続ドロップボックス](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connect G スイート](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Salesforce の接続](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Cisco Webex との接続](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

クラウドアプリを Cloud App Security に接続した後、それらに対して Microsoft 365 DLP ポリシーを作成することができます。

>[!NOTE]
>Microsoft Cloud App Security を使用して、Microsoft クラウドアプリに DLP ポリシーを作成することもできます。 ただし、microsoft 365 を使用して、Microsoft クラウドアプリに DLP ポリシーを作成して管理することをお勧めします。

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウドアプリに DLP ポリシーを作成する

DLP ポリシーの場所を選択する場合は、 **Microsoft Cloud App Security** の場所を有効にします。

- 特定のアプリまたはインスタンスを選択するには、[ **インスタンスの選択**] を選択します。
- インスタンスを選択しない場合、ポリシーは Microsoft Cloud App Security テナント内の接続されているすべてのアプリを使用します。

   ![ポリシーを適用する場所](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![ボックス-US および Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

Microsoft 以外のサポートされているすべてのクラウドアプリに対してさまざまなアクションを選択できます。 すべてのアプリに対して、さまざまなアクションがあります (クラウドアプリ API によって異なります)。

![ルールを作成する](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

DLP ポリシーでルールを作成するときは、Microsoft 以外のクラウドアプリ用のアクションを選択できます。 サードパーティ製アプリを制限するには、[ **サードパーティ製アプリを制限**する] を選択します。

![サードパーティ製アプリを制限する](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

DLP ポリシーの作成および構成の詳細については、「 [Create test and チューン a dlp policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)」を参照してください。

## <a name="see-also"></a>関連項目

- [DLP ポリシーをテストして調整する](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [DLP の既定ポリシーの概要](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [テンプレートからの DLP ポリシーの作成](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
