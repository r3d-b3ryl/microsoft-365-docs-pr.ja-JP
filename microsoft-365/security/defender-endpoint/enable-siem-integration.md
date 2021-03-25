---
title: エンドポイント向け Microsoft Defender で SIEM 統合を有効にする
description: SIEM 統合を有効にして、セキュリティ情報とイベント管理 (SIEM) ソリューションで検出を受け取る。
keywords: SIEM コネクタ、SIEM、コネクタ、セキュリティ情報、イベントを有効にする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068204"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>エンドポイント向け Microsoft Defender で SIEM 統合を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

セキュリティ情報とイベント管理 (SIEM) 統合を有効にして、Microsoft Defender セキュリティ センターから検出を取得できます。 SIEM ソリューションを使用するか、検出 REST API に直接接続して検出をプルします。

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert は](alerts.md) 、1 つ以上の検出から構成されます。
>- [Microsoft Defender for Endpoint Detection は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。
>- Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。 詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。

## <a name="prerequisites"></a>前提条件

- この設定をアクティブ化するユーザーには、Azure Active Directory (AAD) でアプリを作成するためのアクセス許可が必要です。 これは、次の役割を持つユーザーです。 

  - セキュリティ管理者とグローバル管理者
  - クラウド アプリケーション管理者
  - アプリケーション管理者
  - サービス プリンシパルの所有者

- 最初のライセンス認証中に、資格情報を入力するためのポップアップ画面が表示されます。 このサイトのポップアップを許可してください。

## <a name="enabling-siem-integration"></a>SIEM 統合の有効化 
1. ナビゲーション ウィンドウで、[設定 SIEM]**を**  >  **選択します**。

    ![[設定] メニュー 1 からの SIEM 統合のイメージ](images/enable_siem.png)

    >[!TIP]
    >SIEM コネクタ アプリケーションを有効にしようとするときにエラーが発生した場合は、ブラウザーのポップアップ ブロッカー設定を確認してください。 機能を有効にするときに開いている新しいウィンドウがブロックされている可能性があります。 

2. [SIEM **統合を有効にする] を選択します**。 これにより、値が事前に入力された **SIEM** コネクタ アクセスの詳細セクションがアクティブ化され、アプリケーションが Azure Active Directory (Azure Active Directory) テナントのADされます。

    > [!WARNING]
    >クライアント シークレットは 1 回だけ表示されます。 コピーを安全な場所に保管してください。<br>
     

    ![[設定] メニュー 2 からの SIEM 統合のイメージ](images/siem_details.png)

3. 組織で使用する SIEM の種類を選択します。

   > [!NOTE]
   > [HP ArcSight] を選択した場合は、次の 2 つの構成ファイルを保存する必要があります。<br>
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties <br>

   プログラムによるアクセスを使用して検出 REST API に直接接続する場合は、[汎用 **API] を選択します**。

4. 個々の値をコピーするか、[詳細をファイル **に保存** ] を選択して、すべての値を含むファイルをダウンロードします。

5. [トークン **の生成] を** 選択して、アクセス トークンと更新トークンを取得します。
  
   > [!NOTE]
   > 90 日ごとに新しい更新トークンを生成する必要があります。 

6. [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp)の Azure ADアプリ登録を作成する手順に従い、適切なアクセス許可を割り当て、アラートを読み取ってください。

これで、SIEM ソリューションの構成またはプログラムによるアクセスを通じて検出 REST API への接続を続行できます。 SIEM ソリューションを構成するときにトークンを使用して、Microsoft Defender セキュリティ センターから検出を受け取る必要があります。

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>Microsoft Defender for Endpoint と IBM QRadar の統合 
Microsoft Defender for Endpoint から検出を収集するために IBM QRadar を構成できます。 詳細については [、「IBM Knowledge Center」を参照してください](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。

## <a name="see-also"></a>関連項目
- [エンドポイント検出用の Microsoft Defender をプルする HP ArcSight の構成](configure-arcsight.md)
- [Microsoft Defender for Endpoint Detection フィールド](api-portal-mapping.md)
- [REST API を使用したエンドポイント検出用の Microsoft Defender のプル](pull-alerts-using-rest-api.md)
- [SIEM ツールの統合に関する問題のトラブルシューティング](troubleshoot-siem.md)
