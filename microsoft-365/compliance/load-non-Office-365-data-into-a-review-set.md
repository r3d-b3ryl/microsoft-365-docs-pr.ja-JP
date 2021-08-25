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
description: ケース内の分析用にMicrosoft 365データをレビュー セットにインポートする方法についてAdvanced eDiscoveryします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe4863321997ba6b81be2257b6ef44c83bc34cb2
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508264"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>レビューセットにMicrosoft 365 以外のデータを読み込む

ドキュメント内で分析する必要があるすべてのAdvanced eDiscoveryは、Microsoft 365。 Advanced eDiscovery の Microsoft 365 以外のデータインポート機能を使用すると、Microsoft 365 にないドキュメントをレビューセットにアップロードできます。 この記事では、非ドキュメントを分析Microsoft 365にAdvanced eDiscovery示します。

## <a name="requirements-to-upload-non-office-365-content"></a>コンテンツ以外のコンテンツをアップロードOffice 365要件

この記事で説明するアップロードMicrosoft 365機能を使用するには、次の情報が必要です。

- ユーザー以外のコンテンツを関連付けるすべての保管担当者Microsoft 365適切なライセンスが割り当てられている必要があります。 詳細については、「Get [started with Advanced eDiscovery」 を参照してください](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

- 既存のケースAdvanced eDiscoveryします。

- 管理者以外のデータをアップロードして関連付ける前に、保管担当者をケースにMicrosoft 365する必要があります。

- Microsoft 以外の365データは、Advanced eDiscovery でサポートされているファイルの種類である必要があります。 詳細については、[Advanced eDiscovery でサポートされているファイルの種類](supported-filetypes-ediscovery20.md) を参照してください。

- レビュー セットにアップロードされたすべてのファイルは、フォルダーにある必要があります。各フォルダーは、特定のカストディアンに関連付けられています。 これらのフォルダーの名前には、*alias@domainname* のような名前付け形式を使用する必要があります。 alias@domainname は、ユーザーの Microsoft 365 エイリアスとドメインにする必要があります。 ルート フォルダー内のすべてのalias@domainnameを収集できます。 ルート フォルダーには、ルート フォルダー alias@domainnameできます。 ルート フォルダー内の緩いファイルはサポートされていません。

   アップロードするデータMicrosoft 365のフォルダー構造は、次の例のようになります。

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   ここで abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、staci.gonzalez@contoso.com は、ケース内の保管担当者の SMTP アドレスです。

   ![データアップロードMicrosoft 365構造以外](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 電子情報開示マネージャーの役割グループに割り当てられているアカウント (および電子情報開示管理者として追加)。

- コンピューターにインストールされている AzCopy v8.1 ツールで、コンテンツ フォルダー構造以外Microsoft 365アクセスできます。 AzCopy をインストールするには[、「AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)を使用してデータを転送する」を参照Windows。 既定の場所に **、%ProgramFiles(x86)%\Microsoft SDK\Azure\AzCopy** である AzCopy をインストールしてください。 AzCopy v8.1 を使用する必要があります。 他のバージョンの AzCopy は、アプリケーション内のデータを読み込Microsoft 365機能しない場合Advanced eDiscovery。


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>アップロードコンテンツをMicrosoft 365にAdvanced eDiscovery

1. 電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscoveryを開き、非電子情報開示データがアップロードMicrosoft 365ケースに移動します。  

2. [**レビュー セット] を** クリックし、レビュー セットを選択して、ユーザー以外のデータMicrosoft 365アップロードします。  レビュー セットを持ってない場合は、1 つを作成できます。 
 
3. レビュー セットで、 **レビューセットの管理** をクリックし、**Microsoft 以外の365データ** タイルの **アップロードの表示** をクリックします。

4. **ファイルのアップロード** をクリックして、データ インポート ウィザードを開始します。

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   ウィザードの最初の手順で準備するセキュリティで保護された Microsoft 提供の Azure Storage に、ファイルをにアップロードします。  準備が完了したら、**次: ファイルのアップロード** ボタンがアクティブになります。

   ![非インポートMicrosoft 365: 準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. **次: ファイルのアップロード** をクリックします。

6. [ファイルの **アップロード] ページ** で、次の操作を行います。

   ![非インポートMicrosoft 365: アップロード ファイル](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. [ファイル **の場所への** パス] ボックスで、アップロードするデータ以外のデータを保存したルート フォルダーの場所Microsoft 365入力します。 たとえば、[開始する前に] セクションに示されているサンプルファイルの場所については **、「%USERPROFILE\Downloads」と入力し、onO365**\n入力します。 正しい場所を指定すると、パスの下のボックスに表示される AzCopy コマンドが正しく更新されます。

   b. [ **クリップボードにコピー] を** クリックして、ボックスに表示されるコマンドをコピーします。

7. コマンド プロンプトWindowsを開始し、前の手順でコピーしたコマンドを貼り付け **、Enter** キーを押して AzCopy コマンドを開始します。  コマンドを開始すると、手順 4 でMicrosoft 365した場所Azure Storageファイルがアップロードされます。

   ![非Microsoft 365インポート: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 前に述べたように、AzCopy v8.1 を使用して、[ファイルファイル] ページで提供されているコマンドを正常に使用アップロード **必要** があります。 指定された AzCopy コマンドが失敗した場合は、「トラブルシューティング[AzCopy in Advanced eDiscovery」 を参照してください](troubleshooting-azcopy.md)。

8. ウィザードに戻り、[次 **Microsoft 365 コンプライアンス センター: ウィザードでファイルを処理する**] をクリックします。  これにより、Azure Storage の場所にアップロードされた Microsoft 365 以外のファイルの処理、テキスト抽出、インデックス作成が開始されます。  

9. [ファイルの処理] ページまたは[ジョブ] タブでファイルの処理の進行状況を追跡するには、レビュー セットに非ユーザー データMicrosoft 365を追加するという名前のジョブを **表示します**。  ジョブが完了すると、新しいファイルがレビュー セットで使用できます。

   ![非インポートMicrosoft 365: ファイルの処理](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 処理が完了したら、ウィザードを閉じることができます。