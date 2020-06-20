---
title: コネクタをセットアップしてFacebook のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Microsoft 365 コンプライアンスセンターでコネクタを使用 & て、Facebook のビジネスページのアーカイブデータを Microsoft 365 にインポート & をセットアップする方法について説明します。
ms.openlocfilehash: 79f3c3914476a20c07a1c3ab4418b918c8f22c3e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818466"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Facebook データをアーカイブするコネクタを設定する (プレビュー)

Microsoft 365 コンプライアンスセンターのコネクタを使用して、Facebook のビジネスページから Microsoft 365 にデータをインポートし、アーカイブします。 コネクタをセットアップして構成すると、そのコネクタは Facebook のビジネスページに接続し (スケジュールに従って)、Facebook のアイテムのコンテンツを電子メールメッセージの形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

Facebook データのインポート後、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Facebook データに適用することができます。 たとえば、メールボックスが訴訟ホールドの対象となっている場合、またはアイテム保持ポリシーに割り当てられている場合、Facebook データは保持されます。 高度な電子情報開示ケースでは、コンテンツ検索を使用してサードパーティのデータを検索するか、または保管担当者に Facebook データが格納されているメールボックスを関連付けることができます。 コネクタを使用して、Microsoft 365 で Facebook データをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Facebook ビジネスページ用のコネクタを設定するための前提条件

Microsoft 365 コンプライアンスセンターでコネクタを設定および構成して、組織の Facebook ビジネスページからデータをインポートおよびアーカイブする前に、次の前提条件を満たす必要があります。 

- 組織のビジネスページ用の Facebook アカウントが必要です (コネクタを設定するときに、このアカウントにサインインする必要があります)。 現時点では、Facebook のビジネスページのデータのみをアーカイブできます。個別の Facebook プロファイルからデータをアーカイブすることはできません。

- 組織が有効な Azure サブスクリプションを持っている必要があります。 既存の Azure サブスクリプションがない場合は、次のオプションのいずれかにサインアップできます。

    - [無料の1年間の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [Azure へのご購入のサブスクリプションへのサインアップ](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 サブスクリプションに含まれている[無料の Azure Active Directory サブスクリプション](use-your-free-azure-ad-subscription-in-office-365.md)は、セキュリティ & コンプライアンスセンターのコネクタをサポートしていません。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この要求に同意するには、[このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、グローバル管理者の資格情報でサインインし、要求を承諾します。

- Microsoft 365 コンプライアンスセンター (手順 5) でカスタムコネクタをセットアップするユーザーは、Exchange Online でメールボックスのインポートのエクスポート役割を割り当てる必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「[役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)」または「[役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)」のセクションを参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順として、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、手順4および Facebook コネクタの手順5で実装した web app リソースに対応しています。 

詳細な手順については、「 [Azure Active Directory でアプリを作成](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)する」を参照してください。

この手順が完了すると (前述の手順に従って)、次の情報がテキストファイルに保存されます。 これらの値は、展開プロセスの後の手順で使用します。

- AAD アプリケーション ID

- AAD アプリケーションシークレット

- テナント Id

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>手順 2: GitHub から Azure アカウントにコネクタ web サービスを展開する

次の手順では、facebook API を使用して facebook アカウントに接続し、データを抽出して Microsoft 365 にインポートできるようにする facebook Business pages コネクタアプリのソースコードを展開します。 組織用に展開する Facebook コネクタは、Facebook ビジネスページから、この手順で作成された Azure ストレージの場所にアイテムをアップロードします。 Microsoft 365 コンプライアンスセンター (手順 5) で Facebook business pages コネクタを作成すると、インポートサービスによって Azure のストレージの場所から Microsoft 365 組織のメールボックスに Facebook ビジネスページのデータがコピーされます。 前述の「[前提条件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)」セクションで説明したように、azure Storage アカウントを作成するには、有効な azure サブスクリプションを用意する必要があります。

詳細な手順については、「 [connector web service を GitHub から Azure アカウントに展開する](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)」を参照してください。

この手順を完了するための手順については、次の情報を提供します。

- APISecretKey: この手順の完了時にこのシークレットを作成します。 手順5で使用します。

- TenantId: 手順1で Azure Active Directory で Facebook connector アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

この手順を完了したら、Azure app service の URL (たとえば、) を必ずコピーしてください https://fbconnector.azurewebsites.net) 。 手順3、手順4、および手順5を完了するには、この URL を使用する必要があります。

## <a name="step-3-register-the-web-app-on-facebook"></a>手順 3: Facebook で web アプリを登録する

次の手順では、Facebook で新しいアプリを作成して構成します。 手順5で作成した Facebook business pages コネクタは、facebook web アプリを使用して、組織の Facebook ビジネスページからデータを取得する Facebook API と対話します。

詳細な手順については、「 [Facebook アプリを登録する](deploy-facebook-connector.md#step-3-register-the-facebook-app)」を参照してください。

この手順が完了したら (手順に従って)、次の情報をテキストファイルに保存します。 これらの値は、手順4で Facebook connector アプリを構成するために使用されます。

- Facebook アプリケーション ID

- Facebook アプリケーションシークレット

- Facebook webhook でトークンを確認する

## <a name="step-4-configure-the-facebook-connector-app"></a>手順 4: Facebook connector アプリを構成する

次の手順では、手順1で Azure web app リソースの作成時にアップロードした Facebook connector アプリに構成設定を追加します。 これを行うには、コネクタアプリのホームページにアクセスして構成します。

詳細な手順については、「 [Facebook connector アプリを構成する](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)」を参照してください。

この手順が完了すると (手順に従って)、次の情報が提供されます (前の手順を完了した後、テキストファイルにコピーしたことになります)。

- Facebook アプリケーション ID (手順3で取得)

- Facebook アプリケーションシークレット (手順3で取得)

- Facebook webhook でトークンを確認する (手順3で取得)

- Azure Active Directory アプリケーション ID (手順1で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーションシークレット (手順1で取得した AAD アプリケーションシークレット)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンスセンターで Facebook Business pages コネクタを設定する

最後の手順では、Microsoft 365 コンプライアンスセンターで、ユーザーが Facebook のビジネスページから Microsoft 365 の指定したメールボックスにデータをインポートするようにコネクタを設定します。 この手順を完了すると、Office 365 インポートサービスは、Facebook のビジネスページから Microsoft 365 へのデータのインポートを開始します。

詳細な手順については、「 [Microsoft 365 コンプライアンスセンターで手順 5: Facebook コネクタを設定する](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)」を参照してください。 

この手順が完了すると (手順に従って)、次の情報が提供されます (手順を完了した後、テキストファイルにコピーしたことになります)。

- AAD アプリケーション ID (手順1で取得)

- Azure app service の URL (手順1で取得) (例:https://fbconnector.azurewebsites.net)

- APISecretKey (手順2で作成したもの)
