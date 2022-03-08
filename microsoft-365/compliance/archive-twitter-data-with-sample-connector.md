---
title: コネクタセットアップしてTwitter のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタをセットアップして使用して、Twitter データをユーザーにインポートする方法Microsoft 365。
ms.openlocfilehash: 959cdd49d229334f3129eb21505c4489d23ded4f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320635"
---
# <a name="set-up-a-microsoft-connector-to-archive-twitter-data-preview"></a>Microsoft コネクタをセットアップして Twitter データをアーカイブする (プレビュー)

データをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターのコネクタを使用して、Twitter からデータをMicrosoft 365。 コネクタを設定して構成すると、組織の Twitter アカウントに (スケジュールに基づいて) 接続し、アイテムのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用できます。 たとえば、メールボックスが訴訟ホールドに置かれたり、保持ポリシーに割り当てられたりすると、Twitter データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索するか、Twitter データが保存されているメールボックスを管理者に関連付Advanced eDiscoveryできます。 コネクタを使用して Twitter データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をメールボックスに格納されているデータに適用できます。 たとえば、コンテンツ検索を使用して Twitter データを検索したり、データが保管担当者に保存されているメールボックスを特定のケースに関連付Advanced eDiscoveryできます。 コネクタを使用して Twitter データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

組織の Twitter アカウントからデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターコネクタをセットアップして構成する前に、次の前提条件を満たしてください。

- 組織の Twitter アカウントが必要です。コネクタのセットアップ時に、このアカウントにサインインする必要があります。

- 組織に有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [無料の 1 年間 Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [Pay-As-Go Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > サブスクリプション[にAzure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md)されている無料のサブスクリプションは、Microsoft 365のコネクタをサポートMicrosoft 365 コンプライアンス センター。

- Twitter コネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 件を超える Twitter アイテムがある場合、それらのアイテムはいずれも 1 日にインポートMicrosoft 365。

- [データ コネクタ管理者] ロールを (Microsoft 365 コンプライアンス センター 5) の Twitter コネクタを設定するユーザーに割り当てる必要があります。 この役割は、データ コネクタ ページの [データ  コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。 この役割は、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ とコンプライアンス センターのアクセス許可」の「セキュリティとコンプライアンス センターの役割& [してください](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)。 または、組織内の管理者がカスタム役割グループを作成し、データ コネクタ管理者の役割を割り当て、適切なユーザーをメンバーとして追加することもできます。 手順については、「アクセス許可」の「カスタム役割グループを作成する」[セクションを参照Microsoft 365 コンプライアンス センター](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: アプリをアプリで作成Azure Active Directory

最初の手順は、アプリに新しいアプリを登録Azure Active Directory (AAD)。 このアプリは、Twitter コネクタの手順 2 で実装する Web アプリ リソースに対応します。

手順については、「アプリを作成する[」](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)を参照Azure Active Directory。

この手順が完了すると (手順の手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD ID

- AAD シークレット

- テナント ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>手順 2: コネクタ Web サービスを azure GitHubリポジトリから Azure アカウントに展開する

次の手順では、Twitter API を使用して Twitter アカウントに接続してデータを抽出する Twitter コネクタ アプリのソース コードを展開し、そのソース コードを Microsoft 365 にインポートします。 組織に展開する Twitter コネクタは、組織の Twitter アカウントからこの手順で作成Azure Storage場所にアイテムをアップロードします。 Microsoft 365 コンプライアンス センター (手順 5) で Twitter コネクタを作成すると、Microsoft 365 インポート サービスは、Azure Storage の場所から Microsoft 365 のメールボックスに Twitter データをコピーします。 前の「コネクタをセットアップ[する](#before-you-set-up-a-connector)前に」セクションで説明したように、有効な Azure サブスクリプションを持ってアカウントを作成するAzure Storageがあります。

Twitter コネクタ アプリのソース コードを展開するには、次の方法を実行します。

1. このサイト[にGitHubします](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。

2. [ **Azure に展開] をクリックします**。

詳細な手順については、「コネクタ Web サービスを Azure アカウントに展開する」を参照[GitHubを参照してください](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

手順に従ってこの手順を完了する場合は、次の情報を提供します。

- APISecretKey: この手順の完了時に、このシークレットを作成します。 手順 5 で使用します。

- tenantId: 手順 1 で Twitter アプリMicrosoft 365作成した後にコピーした組織のテナント ID Azure Active Directory ID です。

この手順を完了した後、必ずアプリのサービス URL (たとえば) をコピーしてください `https://twitterconnector.azurewebsites.net`。 この URL を使用して、手順 3、手順 4、および手順 5) を完了する必要があります。

## <a name="step-3-create-developer-app-on-twitter"></a>手順 3: Twitter で開発者アプリを作成する

次の手順では、Twitter で開発者アプリを作成して構成します。 手順 7 で作成するカスタム コネクタは、Twitter アプリを使用して Twitter API を操作し、組織の Twitter アカウントからデータを取得します。

手順については、「 [Create the Twitter app」を参照してください](deploy-twitter-connector.md#step-3-create-the-twitter-app)。

この手順の完了時 (手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、手順 4 で Twitter コネクタ アプリを構成するために使用されます。

- Twitter API キー

- Twitter API シークレット キー

- Twitter アクセス トークン

- Twitter アクセス トークン シークレット

## <a name="step-4-configure-the-twitter-connector-app"></a>手順 4: Twitter コネクタ アプリを構成する

次の手順では、手順 2 で展開した Twitter コネクタ アプリに構成設定を追加します。 これを行うには、コネクタ アプリのホーム ページに移動して構成します。

手順については、「コネクタ Web アプリを構成 [する」を参照してください](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。

この手順の完了時 (手順に従って)、次の情報 (前の手順を完了した後にテキスト ファイルにコピーした情報) を提供します。

- Twitter API キー (手順 3 で取得)

- Twitter API シークレット キー (手順 3 で取得)

- Twitter アクセス トークン (手順 3 で取得)

- Twitter Access Token Secret (手順 3 で取得)

- Azure Active Directory ID (手順 1 でAADされたアプリケーション ID)

- Azure Active Directory シークレット (手順 1 でAADアプリケーション シークレット)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>手順 5: アプリケーションで Twitter コネクタをセットアップMicrosoft 365 コンプライアンス センター

最後の手順は、組織の Twitter アカウントから、Microsoft 365 コンプライアンス センター 内の指定されたメールボックスにデータをインポートする Twitter コネクタを Microsoft 365 で設定することです。 この手順を完了すると、Microsoft 365インポート サービスは組織の Twitter アカウントからデータのインポートを開始Microsoft 365。

詳しい手順については、「Twitter コネクタをセットアップする」を参照[Microsoft 365 コンプライアンス センター。](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

この手順の完了時 (手順の手順に従って)、次の情報 (手順を完了した後にテキスト ファイルにコピーした情報) を提供します。

- Azure アプリ サービスの URL (手順 2 で取得、たとえば `https://twitterconnector.azurewebsites.net`)

- APISecretKey (手順 2 で作成した)