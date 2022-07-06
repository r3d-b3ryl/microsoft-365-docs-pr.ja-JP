---
title: Microsoft 以外のクラウド アプリに DLP ポリシーを使用する
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
description: Microsoft 以外のクラウド アプリで DLP ポリシーを使用する方法について説明します。
ms.openlocfilehash: a50849b53819a7c5872c3ec8cb279ffa8d14e27f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634389"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps"></a>Microsoft 以外のクラウド アプリにデータ損失防止ポリシーを使用する

機密アイテムが Microsoft 以外のクラウド アプリで使用され、共有されている場合に、DLP ポリシーのスコープをMicrosoft Defender for Cloud Appsして監視、検出、およびアクションを実行できます。

## <a name="before-you-begin"></a>はじめに

### <a name="skusubscriptions-licensing"></a>SKU /サブスクリプションライセンス

DLP ポリシーの使用を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) とアドオンを確認します。 この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。

- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft 365 E5 Security

### <a name="permissions"></a>アクセス許可
DLP ポリシーを作成するユーザーは、次のようになります。

- 全体管理者
- コンプライアンス管理者: Azure AD で割り当てる
- コンプライアンス データ管理者: Azure AD で割り当てる

### <a name="prepare-your-defender-for-cloud-apps-environment"></a>Defender for Cloud Apps 環境を準備する

Microsoft Defender for Cloud Apps対象の DLP ポリシーを構成する前に、Defender for Cloud Apps 環境を準備する必要があります。 手順については、「[クイック スタート: Microsoft Defender for Cloud Appsの概要](/defender-cloud-apps/get-started)」を参照してください。

### <a name="connect-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウド アプリを接続する

特定の Microsoft 以外のクラウド アプリのスコープである DLP ポリシーを使用するには、アプリを Defender for Cloud Apps に接続する必要があります。 詳細については、次を参照してください。

- [[ボックスの接続]](/defender-cloud-apps/connect-box)
- [Dropbox を接続する](/defender-cloud-apps/connect-dropbox)
- [Google ワークスペースを接続する](/defender-cloud-apps/connect-google-workspace)
- [Salesforce を接続する](/defender-cloud-apps/connect-salesforce)
- [Cisco Webex を接続する](/defender-cloud-apps/connect-webex)

クラウド アプリを Defender for Cloud Apps に接続したら、それらの DLP ポリシーを作成できます。

## <a name="create-a-dlp-policy-scoped-to-a-non-microsoft-cloud-app"></a>Microsoft 以外のクラウド アプリを対象とする DLP ポリシーを作成する

DLP ポリシーを作成する手順については [、「DLP ポリシーの作成、テスト、チューニング](create-test-tune-dlp-policy.md) 」を参照してください。 ポリシーを構成するときは、次の点に注意してください。

- **Microsoft Defender for Cloud Apps** の場所をオンにします。
- 特定のアプリまたはインスタンスを選択するには、[ **インスタンスの選択**] を選択します。 インスタンスを選択しない場合、ポリシーは、Microsoft Defender for Cloud Apps テナント内のすべての接続済みアプリにスコープが適用されます。
- サード パーティのアプリに適用する **アクション** の数から選択できます。 サード パーティ製アプリを制限するには、[サード **パーティアプリの制限** ] を選択し、特定のアクションを選択します。

![接続されたクラウド アプリに適用するアクションの一覧](../media/dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> Microsoft Defender for Cloud Appsにスコープが設定された DLP ポリシーを作成すると、同じポリシーがMicrosoft Defender for Cloud Appsに自動的に作成されます。

## <a name="see-also"></a>関連項目

- [DLP ポリシーのテストと調整を作成する](./create-test-tune-dlp-policy.md)
- [DLP の既定ポリシーの概要](./get-started-with-the-default-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](./create-a-dlp-policy-from-a-template.md)
