---
title: Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する
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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 以外のクラウド アプリで dlp ポリシーを使用する方法について説明します。
ms.openlocfilehash: b374f9b85d41b6dd6a5281e17347dffd414361da
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61109781"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a>Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する

Microsoft 以外のクラウド アプリに対するデータ損失防止 (DLP) ポリシーは、Microsoft 365 DLP スイートの機能の一部であり、これらの機能を使用すると、Microsoft 365 サービス全体で機密性の高いアイテムを検出して保護できます。 すべての Microsoft DLP 製品の詳細については、「データ損失防止について」 [を参照してください](dlp-learn-about-dlp.md)。

DLP ポリシーを Microsoft 以外のクラウド アプリに使用して、機密アイテムが Microsoft 以外のクラウド アプリを介して使用および共有される場合の監視と検出を行います。 これらのポリシーを使用すると、それらのポリシーが正しく使用され保護されていることを確認するために必要な可視性と制御が提供され、危険な動作が危険にさらされるのを防ぐのに役立ちます。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

DLP ポリシーを Microsoft 以外のクラウド アプリに使用する前に、サブスクリプションMicrosoft 365[アドオン](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)を確認してください。 この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft 365 E5 Security

### <a name="permissions"></a>アクセス許可
DLP ポリシーを作成するユーザーは、次のユーザーである必要があります。

- 全体管理者
- コンプライアンス管理者: 管理者に割り当Azure AD
- コンプライアンス データ管理者: 管理者に割り当Azure AD

### <a name="prepare-your-defender-for-cloud-apps-environment"></a>Defender for Cloud Apps 環境の準備

Microsoft 以外のクラウド アプリに対する DLP ポリシーでは、Defender for Cloud Apps DLP 機能が使用されます。 それを使用するには、Defender for Cloud Apps 環境を準備する必要があります。 手順については、「アプリの即時表示、保護、ガバナンスアクションの設定 [」を参照してください](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。

### <a name="connect-a-non-microsoft-cloud-app"></a>Connect Microsoft 以外のクラウド アプリを使用する

DLP ポリシーを Microsoft 以外の特定のクラウド アプリに使用するには、アプリを Defender for Cloud Apps に接続する必要があります。 詳細については、次を参照してください。

- [Connect ボックス](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Connect Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Connect G-Workspace](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Connect Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Connect Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

クラウド アプリを Defender for Cloud Apps に接続した後、そのアプリに対してMicrosoft 365 DLP ポリシーを作成できます。

> [!NOTE]
> Microsoft Defender for Cloud Apps を使用して、Microsoft クラウド アプリに DLP ポリシーを作成することもできます。 ただし、Microsoft クラウド アプリに対して DLP Microsoft 365を作成および管理するには、このポリシーを使用する必要があります。

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウド アプリに DLP ポリシーを作成する

DLP ポリシーの場所を選択する場合は **、Microsoft Defender for Cloud Apps の場所をオン** にしてください。

- 特定のアプリまたはインスタンスを選択するには、[インスタンスの選択] **を選択します**。
- インスタンスを選択しない場合、ポリシーは Microsoft Defender for Cloud Apps テナント内のすべての接続アプリを使用します。

   ![ポリシーを適用する場所。](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US と Box-General。](../media/2-dlp-non-microsoft-cloud-app-box.png)

サポートされている Microsoft 以外のクラウド アプリごとにさまざまなアクションを選択できます。 アプリごとに異なるアクションがあります (クラウド アプリ API によって異なります)。

![ルールを作成します。](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

DLP ポリシーでルールを作成する場合は、Microsoft 以外のクラウド アプリのアクションを選択できます。 サード パーティ製アプリを制限するには、[サードパーティ 製アプリの **制限] を選択します**。

![サード パーティ製アプリを制限する。](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> Microsoft 以外のアプリに適用される DLP ポリシーは、Microsoft Defender for Cloud Apps を使用します。 Microsoft 以外のアプリの DLP ポリシーが作成されると、Microsoft Defender for Cloud Apps で同じポリシーが自動的に作成されます。

DLP ポリシーの作成と構成の詳細については、「テストの作成と DLP ポリシー [の調整」を参照してください](./create-test-tune-dlp-policy.md)。

## <a name="see-also"></a>関連項目

- [DLP ポリシーのテストと調整を作成する](./create-test-tune-dlp-policy.md)
- [DLP の既定ポリシーの概要](./get-started-with-the-default-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](./create-a-dlp-policy-from-a-template.md)
