---
title: SAP SuccessFactors をコンテンツ ソースとして構成Microsoft Viva ラーニング
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: SAP SuccessFactors を学習コンテンツ ソースとして構成する方法については、Microsoft Viva ラーニング。
ms.openlocfilehash: 8e5c8c920934883dec9cd020fbb97a87e546c38c
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60703037"
---
# <a name="configure-sap-successfactors-as-a-content-source-for-microsoft-viva-learning"></a>SAP SuccessFactors をコンテンツ ソースとして構成Microsoft Viva ラーニング

この記事では、SAP SuccessFactors をサードパーティのコンテンツ ソースとして構成する方法をMicrosoft Viva ラーニング。 まず、SuccessFactors ポータルでシステム構成を編集する必要があります。次に、システム 構成を完了する必要Microsoft 365 管理センター。

>[!NOTE]
>ビバ サービスからアクセスラーニングは、Microsoft 製品条項以外の条項に従います。 SAP SuccessFactors コンテンツおよび関連するサービスは、SAP SuccessFactors のプライバシーとサービスの条件に従います。

## <a name="configure-in-your-successfactors-portal"></a>SuccessFactors ポータルで構成する

>[!NOTE]
>これらの手順を完了するには、SuccessFactors に管理者のアクセス許可が必要です。

1. [システム管理構成システム構成] PARTNER_EXTRACTにアクセスして取得できる、構成を編集するために必要なワークフローを  >    >  **取得**  >  **PARTNER_EXTRACT。**

2. PGP ツールを使用して、希望するサイズの PGP キー (公開キー、プライベート キー、プライベート キー パスフレーズ) を生成します。 PGP キーを生成する場合は、RSA アルゴリズムを選択できます。これはお勧めします。 GNUPG ツールは、使用できる PGP キー生成ツールの 1 つです。

3. 構成の次のパラメーターをPARTNER_EXTRACTします。 SuccessFactors でパートナー抽出構成を編集するには、SuccessFactors の **[システム構成** の編集] ワークフローのアクセス許可が必要です。

    - すべてのジョブの状態に関する顧客通知メール
        - defaultJob.email=
    
    - Partner1
        - PartnerID の最大長は 10 文字です。 これは、LMS テナント ID です。
    partners1.partnerID=
    
    - EncryptionKey は PGP 公開暗号化キーです。これは BEGIN PGP 公開キー ブロックと END PGP 公開キー ブロックの間のセクション全体です。
        - partners1.encryptionKey=
    
    - KeyOwner が公開キーの User-ID にマップされる
        - partners1.keyOwner=
    
    - 有効にできる値は "false" または "true" です。 パートナー抽出を有効にするには、"true" に設定します。
        - partners1.enabled=
    
    <!--![Image of the PARTNER_EXTRACT configuration settings filled in.](../media/learning/sap-1.png)-->

SuccessFactors ポータルでこれらの手順を完了したら、次の手順でセットアップを完了Microsoft 365 管理センター。

## <a name="configure-in-your-microsoft-365-admin-center"></a>サーバーで構成Microsoft 365 管理センター

>[!NOTE]
>これらの手順を実行するには、管理者のアクセス許可Microsoft 365必要があります。

1. ユーザーに移動[Microsoft 365 管理センター。](https://admin.microsoft.com)

2. [組織の設定 **設定**  >  **移動します**。 オプションから *Viva ラーニング* を検索し、SAP SuccessFactors を有効にします。

3. 構成の詳細を入力します。

    **表示名**: SAP SuccessFactors カルーセルの目的の表示名を入力します。

    **SFTP ホスト URL**: **[LMS Admin Application System**  >  **Administration** Configuration  >  **System Configuration**  >    >  **CONNECTORS] に移動します**。 プロパティの値を取得 `connector.ftp.server` します。

    **ユーザー名**: SFTP ホスト URL に対して実行したのと同じ手順に従います。 プロパティの値を取得 `connector.ftp.userID` します。

    **パスワード**: パスワードを入力します。 LMS アプリケーションの所有者に、パスワードの取得に関するヘルプを確認してください。

    **フォルダーパス**: **[LMS Admin Application System**  >  **Administration**  >  **Configuration System**  >  **Configuration] PARTNER_EXTRACT**  >  に **移動** します。 プロパティの値を取得 `defaultFtp.path` します。

    **クライアントのホスト URL**: これは BizX ドメイン URL です。 これを BizX ログイン URL から取得できます。 たとえば、BizX ログイン URL がホスト URL の場合は `organization.successfactors.com/sf/start/#/login` 、 です `organization.successfactors.com` 。

    **クライアントのラーニング URL**: ラーニング ドメイン モジュールの URL からこれを取得できます。 たとえば、ラーニング ドメイン URL が [宛先 URL] のラーニング `organization.scdemo.successfactors.com/learning/...` 場合です `organization.scdemo.successfactors.com` 。

    **PGP 秘密キー**: 暗号化解除用の PGP 秘密キー。これは BEGIN PGP 秘密キー ブロックと END PGP 秘密キー ブロックの間のセクション全体です。 生成されたキーとまったく同じ方法でキーをコピーする必要があります。新しい行の文字は削除しません。

    **PGP のプライベート キー パス** フレーズ: IT 管理者または PGP キーを提供するチームからこの値を取得する必要があります。

    **会社 ID**: SuccessFactors ポータルにサインインします。 プロファイル アイコンを選択し、[バージョンを **表示する] を設定。** 会社 ID は、こちらから確認できます。

4. [**保存] を** 選択して、次のページで SuccessFactors Microsoft Viva ラーニング。 コンテンツがビバ サービスで利用できるまでに遅れが生ラーニング。

>[!Note]
> SuccessFactors コースは、セットアップが成功したラーニング 7 日以内にビバ のページに表示されます。

>[!Note]
> 組織内のすべてのユーザーは、テナント固有のすべてのコースを検出できますが、アクセスできるコースにのみアクセスおよび使用できます。 ユーザー固有のコンテンツ検出は、今後のリリースに向け計画されています。

>[!NOTE]
>テナント のメタデータは、データ ストアに集中して格納され、地域固有のデータ ストアには格納されません。

>[!NOTE]
>現在、組織内のすべてのユーザーは、テナント固有のすべてのコースを検出できますが、アクセスできるコースのみを使用できます。 ロールとアクセス許可に基づくユーザー固有のコンテンツ検出は、今後のリリースに向け計画されています。
