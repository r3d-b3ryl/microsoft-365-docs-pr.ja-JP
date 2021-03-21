---
title: Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する (プレビュー)
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
description: Microsoft 以外のクラウド アプリで dlp ポリシーを使用する方法について説明します。
ms.openlocfilehash: 6787add3ef8b2d6ded22bd05c0ff9658c4b7fbfc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922083"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する (プレビュー)

Microsoft 以外のクラウド アプリに対するデータ損失防止 (DLP) ポリシーは、Microsoft 365 DLP スイートの機能の一部です。これらの機能を使用すると、Microsoft 365 サービス全体で機密性の高いアイテムを検出して保護できます。 すべての Microsoft DLP 製品の詳細については、「データ損失防止の [概要」を参照してください](./data-loss-prevention-policies.md?view=o365-worldwide)。

DLP ポリシーを Microsoft 以外のクラウド アプリに使用して、機密アイテムが Microsoft 以外のクラウド アプリを介して使用および共有される場合の監視と検出を行います。 これらのポリシーを使用すると、それらのポリシーが正しく使用され保護されていることを確認するために必要な可視性と制御が提供され、危険な動作が危険にさらされるのを防ぐのに役立ちます。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

DLP ポリシーを Microsoft 以外のクラウド アプリに使用する前に [、Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) サブスクリプションとアドオンを確認してください。 この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft 365 E5 Security

### <a name="prepare-your-cloud-app-security-environment"></a>クラウド アプリのセキュリティ環境を準備する

Microsoft 以外のクラウド アプリに対する DLP ポリシーでは、Cloud App Security DLP 機能を使用します。 それを使用するには、Cloud App Security 環境を準備する必要があります。 手順については、「アプリの即時表示、保護、ガバナンスアクションの設定 [」を参照してください](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。

### <a name="connect-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウド アプリを接続する

特定の Microsoft 以外のクラウド アプリに DLP ポリシーを使用するには、アプリを Cloud App Security に接続する必要があります。 詳細については、次を参照してください。

- [Connect Box](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Dropbox の接続](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connect G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Salesforce の接続](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Cisco Webex の接続](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

クラウド アプリを Cloud App Security に接続した後、Microsoft 365 DLP ポリシーを作成できます。

>[!NOTE]
>Microsoft Cloud App Security を使用して、Microsoft クラウド アプリに DLP ポリシーを作成することもできます。 ただし、Microsoft 365 を使用して、Microsoft クラウド アプリに対する DLP ポリシーを作成および管理する方法をお勧めします。

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウド アプリに DLP ポリシーを作成する

DLP ポリシーの場所を選択する場合は **、Microsoft Cloud App Security の場所をオン** にしてください。

- 特定のアプリまたはインスタンスを選択するには、[インスタンスの選択] **を選択します**。
- インスタンスを選択しない場合、ポリシーは Microsoft Cloud App Security テナント内のすべての接続アプリを使用します。

   ![ポリシーを適用する場所](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US と Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

サポートされている Microsoft 以外のクラウド アプリごとにさまざまなアクションを選択できます。 アプリごとに異なるアクションがあります (クラウド アプリ API によって異なります)。

![ルールを作成する](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

DLP ポリシーでルールを作成する場合は、Microsoft 以外のクラウド アプリのアクションを選択できます。 サード パーティ製アプリを制限するには、[サードパーティ 製アプリの **制限] を選択します**。

![サード パーティ製アプリの制限](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

DLP ポリシーの作成と構成の詳細については、「テストの作成と DLP ポリシー [の調整」を参照してください](./create-test-tune-dlp-policy.md?view=o365-worldwide)。

## <a name="see-also"></a>関連項目

- [DLP ポリシーのテストと調整を作成する](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [DLP の既定ポリシーの概要](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [テンプレートからの DLP ポリシーの作成](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)