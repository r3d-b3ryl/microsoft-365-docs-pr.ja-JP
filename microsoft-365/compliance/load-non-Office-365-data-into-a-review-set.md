---
title: レビューセットにMicrosoft 365 以外のデータを読み込む
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 高度な電子情報開示ケースで分析のために Microsoft 以外の365データをレビューセットにインポートする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285863"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>レビューセットにMicrosoft 365 以外のデータを読み込む

Advanced eDiscovery で分析する必要があるすべてのドキュメントが Microsoft 365 にあるわけではありません。 Advanced eDiscovery の Microsoft 365 以外のデータインポート機能を使用すると、Microsoft 365 にないドキュメントをレビューセットにアップロードできます。 この記事では、Microsoft 以外の365ドキュメントを分析のために上級電子情報開示に移行する方法について説明します。

## <a name="requirements-to-upload-non-office-365-content"></a>Office 以外の365コンテンツをアップロードするための要件

この記事に記載されている 365 Microsoft 以外のアップロードをアップロードする機能を使用するには、次のものが必要です。

- Microsoft 以外の365コンテンツに関連付ける必要があるすべての保管担当者には、適切なライセンスが割り当てられている必要があります。 詳細については、「 [Advanced eDiscovery の概要](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)」を参照してください。

- 既存の高度な電子情報開示ケース。

- Microsoft 以外の365データをアップロードして関連付けするには、その前に保管担当者をケースに追加する必要があります。

- Microsoft 以外の365データは、Advanced eDiscovery でサポートされているファイルの種類である必要があります。 詳細については、[Advanced eDiscovery でサポートされているファイルの種類](supported-filetypes-ediscovery20.md) を参照してください。

- レビュー セットにアップロードされたすべてのファイルは、フォルダーにある必要があります。各フォルダーは、特定のカストディアンに関連付けられています。 これらのフォルダーの名前には、*alias@domainname*のような名前付け形式を使用する必要があります。 alias@domainname は、ユーザーの Microsoft 365 エイリアスとドメインにする必要があります。 ルートフォルダー内のすべての alias@domainname フォルダーを収集できます。 ルートフォルダーには alias@domainname フォルダーのみ含めることができます。 ルートフォルダー内のルースファイルはサポートされていません。

   アップロードする Microsoft 以外の365データのフォルダー構造は、次の例のようになります。

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   この例では、abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、および staci.gonzalez@contoso.com は、保管担当者の SMTP アドレスです。

   ![Microsoft 以外の365データアップロードフォルダーの構造](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 電子情報開示マネージャーの役割グループに割り当てられているアカウント (および電子情報開示管理者として追加されたもの)。

- Microsoft 以外の365コンテンツフォルダー構造にアクセスできるコンピューターにインストールされている AzCopy v2.0 ツール。 AzCopy をインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 を使用してデータを転送する」を参照してください。 AzCopy は、既定の場所である **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**にインストールしてください。 AzCopy v1.1 を使用する必要があります。 その他のバージョンの AzCopy は、高度な電子情報開示で Microsoft 以外の365データを読み込む場合には機能しない可能性があります。


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Microsoft 以外の365コンテンツを上級電子情報開示にアップロードする

1. 電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開いて、Microsoft 以外の365データがアップロードされるケースに進みます。  

2. [ **チェックセット**] をクリックし、[Microsoft 以外の365データをアップロードするためのレビューセット] を選択します。  レビューセットを持っていない場合は、作成できます。 
 
3. レビュー セットで、 **レビューセットの管理** をクリックし、**Microsoft 以外の365データ** タイルの **アップロードの表示** をクリックします。

4. **ファイルのアップロード** をクリックして、データ インポート ウィザードを開始します。

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   ウィザードの最初の手順で準備するセキュリティで保護された Microsoft 提供の Azure Storage に、ファイルをにアップロードします。  準備が完了したら、**次: ファイルのアップロード** ボタンがアクティブになります。

   ![Microsoft 以外の365インポート: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. **次: ファイルのアップロード** をクリックします。

6. [ **ファイルのアップロード** ] ページで、次の操作を行います。

   ![Microsoft 以外の365インポート: ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a.  [ **ファイルの場所のパス** ] ボックスに、アップロードする Microsoft 以外の365データを格納したルートフォルダーの場所を確認するか、または入力します。 たとえば、[ **開始する前に] セクション**に表示されるサンプルファイルの場所については、「 **%USERPROFILE\Downloads\nonO365**」と入力します。 正しい場所を指定すると、パスの下のボックスに表示される AzCopy コマンドが適切に更新されるようになります。

   b.  [ **クリップボードにコピー** ] をクリックして、ボックスに表示されているコマンドをコピーします。

7. Windows コマンドプロンプトを起動し、前の手順でコピーしたコマンドを貼り付け、 **enter** キーを押して、azcopy コマンドを開始します。  コマンドを開始すると、Microsoft 以外の365ファイルは、手順4で準備した Azure ストレージの場所にアップロードされます。

   ![Microsoft 以外の365インポート: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 前述したように、[ **ファイルのアップロード** ] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。 指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。

8. セキュリティ & コンプライアンスセンターに戻り、[ **次へ:** ウィザードでファイルを処理します] をクリックします。  これにより、Azure Storage の場所にアップロードされた Microsoft 365 以外のファイルの処理、テキスト抽出、インデックス作成が開始されます。  

9. 「 **プロセスファイル** 」ページまたは「 **ジョブ** 」タブでファイルの処理の進行状況を追跡するには、「 **Microsoft 以外の365データをレビューセットに追加する**」という名前のジョブを表示します。  ジョブが完了すると、新しいファイルがレビューセットで利用できるようになります。

   ![Microsoft 以外の365インポート: プロセスファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 処理が完了したら、ウィザードを閉じることができます。
