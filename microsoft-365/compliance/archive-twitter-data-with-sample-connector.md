---
title: コネクタセットアップしてTwitter のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/08/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタを設定して使用して Twitter データを Microsoft 365 にインポートする方法について説明します。
ms.openlocfilehash: 1dd5de91484d04411b5216f6801589b32ef381ce
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625557"
---
# <a name="set-up-a-microsoft-connector-to-archive-twitter-data-preview"></a>Twitter データをアーカイブする Microsoft コネクタを設定する (プレビュー)

Microsoft Purview コンプライアンス ポータルのコネクタを使用して、Twitter から Microsoft 365 にデータをインポートおよびアーカイブします。 コネクタを設定して構成すると、組織の Twitter アカウントに接続され (スケジュールに従って)、アイテムのコンテンツが電子メール メッセージ形式に変換され、そのアイテムが Microsoft 365 のメールボックスにインポートされます。

Twitter データがインポートされたら、訴訟ホールド、コンテンツ検索、In-Placeアーカイブ、監査、Microsoft 365 アイテム保持ポリシーなどの Microsoft Purview 機能を Twitter データに適用できます。 たとえば、メールボックスを訴訟ホールドに置いたり、アイテム保持ポリシーに割り当てたりすると、Twitter データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索したり、Twitter データが保存されているメールボックスをMicrosoft Purview eDiscovery (Premium) ケースのカストディアンに関連付けることができます。 コネクタを使用して Microsoft 365 で Twitter データをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

Twitter データをインポートした後は、訴訟ホールド、コンテンツ検索、In-Placeアーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft Purview 機能をメールボックスに格納されているデータに適用できます。 たとえば、コンテンツ検索を使用して Twitter データを検索したり、データが格納されているメールボックスを電子情報開示 (Premium) ケースのカストディアンに関連付けることができます。 コネクタを使用して Microsoft 365 で Twitter データをインポートおよびアーカイブすると、組織が政府および規制のポリシーに準拠し続けることができます。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

コンプライアンス ポータルでコネクタを設定して構成し、組織の Twitter アカウントからデータをインポートおよびアーカイブする前に、次の前提条件を満たしてください。

- 組織には Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。

- 組織に有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [無料の 1 年間の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [従量課金制 Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 [サブスクリプションに含まれる無料の Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) サブスクリプションは、コンプライアンス ポータルのコネクタをサポートしていません。

- Twitter コネクタは、1 日に合計 200,000 個のアイテムをインポートできます。 1 日に 200,000 件を超える Twitter アイテムがある場合、これらのアイテムは Microsoft 365 にインポートされません。

- コンプライアンス ポータルで Twitter コネクタを設定するユーザー (手順 5) には、Data Connector 管理 ロールが割り当てられている必要があります。 このロールは、コンプライアンス ポータルの **[データ コネクタ** ] ページでコネクタを追加するために必要です。 このロールは、既定で複数の役割グループに追加されます。 これらの役割グループの一覧については、「セキュリティ & コンプライアンス センターのアクセス許可」の「 [セキュリティとコンプライアンス センターの](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)ロール」セクションを参照してください。 または、組織内の管理者がカスタムロール グループを作成し、Data Connector 管理ロールを割り当ててから、適切なユーザーをメンバーとして追加することもできます。 手順については、[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group)の「カスタム ロール グループの作成」セクションを参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、Twitter コネクタの手順 2 で実装した Web アプリ リソースに対応します。

詳細な手順については、「 [Azure Active Directory でアプリを作成する」を](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)参照してください。

この手順が完了したら (手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、デプロイ プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーション シークレット

- テナント ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>手順 2: GitHub リポジトリから Azure アカウントにコネクタ Web サービスをデプロイする

次の手順では、Twitter API を使用して Twitter アカウントに接続し、Microsoft 365 にインポートできるようにデータを抽出する Twitter コネクタ アプリのソース コードをデプロイします。 組織にデプロイする Twitter コネクタは、組織の Twitter アカウントから、この手順で作成された Azure Storage の場所にアイテムをアップロードします。 コンプライアンス ポータル (手順 5) で Twitter コネクタを作成すると、Microsoft 365 Import サービスによって、Azure Storage の場所から Microsoft 365 のメールボックスに Twitter データがコピーされます。 「 [コネクタをセットアップする前](#before-you-set-up-a-connector) に」セクションで説明したように、Azure Storage アカウントを作成するには、有効な Azure サブスクリプションが必要です。

Twitter コネクタ アプリのソース コードをデプロイするには:

1. [この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)に移動します。

2. [ **Azure へのデプロイ]** をクリックします。

詳細な手順については、「 [GitHub から Azure アカウントにコネクタ Web サービスをデプロイする」を参照してください](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

この手順を完了するには、ステップバイステップの手順に従いながら、次の情報を入力します。

- APISecretKey: この手順の完了時に、このシークレットを作成します。 手順 5. で使用します。

- tenantId: 手順 1 で Azure Active Directory で Twitter アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

この手順を完了したら、アプリ サービスの URL (たとえば) `https://twitterconnector.azurewebsites.net`をコピーしてください。 手順 3、手順 4、および手順 5) を完了するには、この URL を使用する必要があります。

## <a name="step-3-create-developer-app-on-twitter"></a>手順 3: Twitter で開発者アプリを作成する

次の手順では、Twitter で開発者アプリを作成して構成します。 手順 7 で作成したカスタム コネクタでは、Twitter アプリを使用して Twitter API と対話し、組織の Twitter アカウントからデータを取得します。

詳細な手順については、「 [Twitter アプリの作成」を](deploy-twitter-connector.md#step-3-create-the-twitter-app)参照してください。

この手順が完了したら (手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、手順 4. で Twitter コネクタ アプリを構成するために使用されます。

- Twitter API キー

- Twitter API シークレット キー

- Twitter アクセス トークン

- Twitter アクセス トークン シークレット

## <a name="step-4-configure-the-twitter-connector-app"></a>手順 4: Twitter コネクタ アプリを構成する

次の手順では、手順 2. でデプロイした Twitter コネクタ アプリに構成設定を追加します。 これを行うには、コネクタ アプリのホーム ページに移動し、構成します。

詳細な手順については、「 [コネクタ Web アプリの構成](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)」を参照してください。

この手順が完了したら (手順に従って)、次の情報 (前の手順を完了した後にテキスト ファイルにコピーした情報) を指定します。

- Twitter API キー (手順 3 で取得)

- Twitter API シークレット キー (手順 3 で取得)

- Twitter アクセス トークン (手順 3 で取得)

- Twitter アクセス トークン シークレット (手順 3 で取得)

- Azure Active Directory アプリケーション ID (手順 1 で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)

## <a name="step-5-set-up-a-twitter-connector-in-the-compliance-portal"></a>手順 5: コンプライアンス ポータルで Twitter コネクタを設定する

最後の手順では、コンプライアンス ポータルで Twitter コネクタを設定し、組織の Twitter アカウントから Microsoft 365 の指定されたメールボックスにデータをインポートします。 この手順を完了すると、Microsoft 365 Import サービスは組織の Twitter アカウントから Microsoft 365 へのデータのインポートを開始します。

詳細な手順については、[Microsoft Purview コンプライアンス ポータルでの Twitter コネクタのセットアップに関する記事を参照](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-compliance-portal)してください。

この手順の完了時に (手順に従って)、次の情報 (手順の完了後にテキスト ファイルにコピーした情報) を指定します。

- Azure App Service URL (手順 2 で取得。たとえば) `https://twitterconnector.azurewebsites.net`

- APISecretKey (手順 2 で作成した)