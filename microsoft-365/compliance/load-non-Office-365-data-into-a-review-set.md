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
description: 高度な電子情報開示ケースで分析用のレビュー セットに Microsoft 365 以外のデータをインポートする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903503"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>レビューセットにMicrosoft 365 以外のデータを読み込む

高度な電子情報開示で分析する必要があるすべてのドキュメントが Microsoft 365 にあるという場合があります。 Advanced eDiscovery の Microsoft 365 以外のデータインポート機能を使用すると、Microsoft 365 にないドキュメントをレビューセットにアップロードできます。 この記事では、分析のために Microsoft 365 以外のドキュメントを Advanced eDiscovery に取り込む方法について説明します。

## <a name="requirements-to-upload-non-office-365-content"></a>365 以外のコンテンツをアップロードOffice要件

この記事で説明されている Microsoft 365 以外のアップロード機能を使用するには、次の情報が必要です。

- Microsoft 365 以外のコンテンツを関連付けるすべての保管担当者に、適切なライセンスを割り当てる必要があります。 詳細については、「高度な電子 [情報開示の使用を開始する」を参照してください](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

- 既存の Advanced 電子情報開示ケース。

- Microsoft 365 以外のデータをアップロードして関連付ける前に、カストディアンをケースに追加する必要があります。

- Microsoft 以外の365データは、Advanced eDiscovery でサポートされているファイルの種類である必要があります。 詳細については、[Advanced eDiscovery でサポートされているファイルの種類](supported-filetypes-ediscovery20.md) を参照してください。

- レビュー セットにアップロードされたすべてのファイルは、フォルダーにある必要があります。各フォルダーは、特定のカストディアンに関連付けられています。 これらのフォルダーの名前には、*alias@domainname* のような名前付け形式を使用する必要があります。 alias@domainname は、ユーザーの Microsoft 365 エイリアスとドメインにする必要があります。 ルート フォルダー内のすべてのalias@domainnameを収集できます。 ルート フォルダーには、ルート フォルダー alias@domainnameできます。 ルート フォルダー内の緩いファイルはサポートされていません。

   アップロードする Microsoft 365 以外のデータのフォルダー構造は、次の例のようになります。

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   ここで abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、staci.gonzalez@contoso.com は、ケース内の保管担当者の SMTP アドレスです。

   ![Microsoft 365 以外のデータアップロード フォルダー構造](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 電子情報開示マネージャーの役割グループに割り当てられているアカウント (および電子情報開示管理者として追加)。

- Microsoft 365 以外のコンテンツ フォルダー構造にアクセスできるコンピューターにインストールされている AzCopy v8.1 ツール。 AzCopy をインストールするには [、「Windows で AzCopy v8.1 を](/previous-versions/azure/storage/storage-use-azcopy)使用してデータを転送する」を参照してください。 既定の場所に **、%ProgramFiles(x86)%\Microsoft SDK\Azure\AzCopy** である AzCopy をインストールしてください。 AzCopy v8.1 を使用する必要があります。 高度な電子情報開示で Microsoft 365 以外のデータを読み込む場合、AzCopy の他のバージョンが機能しない場合があります。


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Microsoft 365 以外のコンテンツを Advanced eDiscovery にアップロードする

1. 電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開き、Microsoft 365 以外のデータがアップロードされる場合に移動します。  

2. [ **レビュー セット]** をクリックし、レビュー セットを選択して Microsoft 365 以外のデータをアップロードします。  レビュー セットを持ってない場合は、1 つを作成できます。 
 
3. レビュー セットで、 **レビューセットの管理** をクリックし、**Microsoft 以外の365データ** タイルの **アップロードの表示** をクリックします。

4. **ファイルのアップロード** をクリックして、データ インポート ウィザードを開始します。

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   ウィザードの最初の手順で準備するセキュリティで保護された Microsoft 提供の Azure Storage に、ファイルをにアップロードします。  準備が完了したら、**次: ファイルのアップロード** ボタンがアクティブになります。

   ![Microsoft 365 以外のインポート: 準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. **次: ファイルのアップロード** をクリックします。

6. [ファイルの **アップロード] ページ** で、次の操作を行います。

   ![Microsoft 365 以外のインポート: ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. [ファイル **の場所への** パス] ボックスで、アップロードする Microsoft 365 以外のデータを保存したルート フォルダーの場所を確認または入力します。 たとえば、「開始する前に」セクションに示されているサンプルファイルの場所に **「%USERPROFILE\Downloads\nonO365」** と入力します。 正しい場所を指定すると、パスの下のボックスに表示される AzCopy コマンドが正しく更新されます。

   b. [ **クリップボードにコピー] を** クリックして、ボックスに表示されるコマンドをコピーします。

7. Windows コマンド プロンプトを開始し、前の手順でコピーしたコマンドを貼り付け **、Enter** キーを押して AzCopy コマンドを開始します。  コマンドを開始すると、手順 4 で準備した Azure Storage の場所に Microsoft 365 以外のファイルがアップロードされます。

   ![Microsoft 365 以外のインポート: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 前に述べたように、[ファイルのアップロード] ページで提供されているコマンドを正常に使用するには、AzCopy v8.1 **を使用する必要** があります。 指定された AzCopy コマンドが失敗した場合は [、「Advanced eDiscovery の AzCopy のトラブルシューティング」を参照してください](troubleshooting-azcopy.md)。

8. [セキュリティ] コンプライアンス センターに&し、ウィザードで [次 **へ: ファイルの処理]** をクリックします。  これにより、Azure Storage の場所にアップロードされた Microsoft 365 以外のファイルの処理、テキスト抽出、インデックス作成が開始されます。  

9. [ファイルの処理] ページまたは[ジョブ] タブで、レビュー セットに **Microsoft 365** 以外のデータを追加するという名前のジョブを表示して、ファイルの処理の進行状況を追跡します。  ジョブが完了すると、新しいファイルがレビュー セットで使用できます。

   ![Microsoft 365 以外のインポート: プロセス ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 処理が完了したら、ウィザードを閉じることができます。