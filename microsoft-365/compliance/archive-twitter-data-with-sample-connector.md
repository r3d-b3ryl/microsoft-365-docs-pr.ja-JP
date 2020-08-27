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
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Twitter データを Microsoft 365 にインポートするために、管理者がネイティブコネクタをセットアップして使用する方法について説明します。
ms.openlocfilehash: 15434899eb90f26205907c474b8d2238db536948
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255844"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>コネクタをアーカイブ Twitter データに設定する (プレビュー)

Microsoft 365 コンプライアンスセンターのコネクタを使用して、Twitter から Microsoft 365 にデータをインポートおよびアーカイブします。 コネクタをセットアップして構成すると、組織の Twitter アカウントに (スケジュールに従って) 接続され、アイテムのコンテンツが電子メールメッセージの形式に変換されてから、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

Twitter データがインポートされたら、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用することができます。 たとえば、メールボックスが訴訟ホールドの対象となっている場合、またはアイテム保持ポリシーに割り当てられている場合、Twitter データは保持されます。 高度な電子情報開示ケースでは、コンテンツ検索を使用してサードパーティのデータを検索したり、Twitter データが格納されているメールボックスを保管担当者に関連付けることができます。 コネクタを使用して、Microsoft 365 で Twitter データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

Twitter データがインポートされたら、メールボックスに格納されているデータに、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を適用できます。 たとえば、コンテンツ検索を使用して Twitter データを検索したり、保管担当者でデータが格納されているメールボックスを、高度な電子情報開示ケースに関連付けたりすることができます。 コネクタを使用して、Microsoft 365 で Twitter データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Twitter 用のコネクタを設定するための前提条件

Microsoft 365 コンプライアンスセンターでコネクタを設定および構成して、組織の Twitter アカウントからデータをインポートおよびアーカイブする前に、次の前提条件を満たしている必要があります。

- 組織のために Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。

- 組織が有効な Azure サブスクリプションを持っている必要があります。 既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。

    - [無料の1年間の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [Azure へのご購入のサブスクリプションへのサインアップ](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 サブスクリプションに含まれている [無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md) は、セキュリティ & コンプライアンスセンターのコネクタをサポートしていません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、グローバル管理者の資格情報でサインインし、要求を承諾します。

- Microsoft 365 コンプライアンスセンター (手順 5) で Twitter connector をセットアップするユーザーは、Exchange Online でメールボックスのインポートのエクスポート役割を割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「  [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順として、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、Twitter connector の手順2で実装した web app リソースに対応します。

詳細な手順については、「 [Azure Active Directory でアプリを作成](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)する」を参照してください。

この手順が完了すると (手順に従って)、次の情報がテキストファイルに保存されます。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーションシークレット

- テナント Id

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>手順 2: GitHub リポジトリから Azure アカウントに connector web サービスを展開する

次の手順では、twitter API を使用して twitter アカウントに接続し、データを抽出して Microsoft 365 にインポートできるようにするための twitter コネクタアプリのソースコードを展開します。 組織用に展開する Twitter コネクタは、組織の Twitter アカウントから、この手順で作成された Azure ストレージの場所にアイテムをアップロードします。 Microsoft 365 コンプライアンスセンター (手順 5) で Twitter コネクタを作成した後、Office 365 インポートサービスは、Azure ストレージの場所から Twitter データを Microsoft 365 のメールボックスにコピーします。 前述の「 [前提条件](#prerequisites-for-setting-up-a-connector-for-twitter) 」セクションで説明したように、azure Storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。

Twitter connector アプリのソースコードを展開するには、次のようにします。

1. [この GitHub サイト](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)に移動します。

2. [ **Azure への展開] を**クリックします。

詳細な手順については、「 [connector web service を GitHub から Azure アカウントに展開する](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)」を参照してください。

手順に従ってこの手順を完了すると、次の情報が提供されます。

- APISecretKey: この手順の完了時にこのシークレットを作成します。 手順5で使用します。

- tenantId: 手順1で作成した、Azure Active Directory で Twitter アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

この手順を完了したら、必ず app Service の URL (例:) をコピーしてください `https://twitterconnector.azurewebsites.net` 。 手順3、手順4、および手順5を完了するには、この URL を使用する必要があります。

## <a name="step-3-create-developer-app-on-twitter"></a>手順 3: Twitter で開発者用アプリを作成する

次の手順では、Twitter で開発者用アプリを作成して構成します。 手順7で作成したカスタムコネクタは、twitter アプリを使用して、組織の Twitter アカウントからデータを取得する Twitter API と対話します。

詳細な手順については、「 [Twitter アプリを作成](deploy-twitter-connector.md#step-3-create-the-twitter-app)する」を参照してください。

この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。 これらの値は、手順4で Twitter connector アプリを構成するために使用されます。

- Twitter API キー

- Twitter API の秘密キー

- Twitter アクセストークン

- Twitter アクセストークンシークレット

## <a name="step-4-configure-the-twitter-connector-app"></a>手順 4: Twitter connector アプリを構成する

次の手順では、手順2で展開した Twitter connector アプリに構成設定を追加します。 これを行うには、コネクタアプリのホームページにアクセスして構成します。

詳細な手順については、「 [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)」を参照してください。

この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。

- Twitter API キー (手順3で取得)

- Twitter API の秘密キー (手順3で取得)

- Twitter アクセストークン (手順3で取得)

- Twitter アクセストークンシークレット (手順3で取得)

- Azure Active Directory アプリケーション ID (手順1で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーションシークレット (手順1で取得した AAD アプリケーションシークレット)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンスセンターで Twitter connector をセットアップする

最後の手順として、Microsoft 365 コンプライアンスセンターで、組織の Twitter アカウントから Microsoft 365 の指定したメールボックスにデータをインポートする Twitter コネクタを設定します。 この手順を完了すると、Office 365 インポートサービスは、組織の Twitter アカウントから Microsoft 365 へのデータのインポートを開始します。

詳細な手順については、「 [Microsoft 365 コンプライアンスセンターでの Twitter コネクタの設定](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)」を参照してください。 

この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了したら、テキストファイルにコピーしたことになります)。

- Azure app service の URL (手順2で取得) (例: `https://twitterconnector.azurewebsites.net` )

- APISecretKey (手順2で作成したもの)
