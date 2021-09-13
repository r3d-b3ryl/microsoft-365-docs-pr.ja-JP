---
title: メールとデータをユーザーに移動Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1062115d-e312-482a-bb5a-765235990f41
ROBOTS: NOINDEX
description: 新しいビジネス ID にデータを移動する方法について学習します。
ms.openlocfilehash: 4f105e00ab6496a5d1d3edfc0e0f1abd4eced412
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59178808"
---
# <a name="move-email-and-data-to-microsoft-365-business-standard"></a>メールとデータをユーザーに移動Microsoft 365 Business Standard

ユーザーが新しいビジネス Microsoft 365 Business Standardにアップグレードすると、新しいビジネス ID が *提供されます*。 新しいメール アカウントと、ビジネス データ用に個別の OneDrive アカウントを利用できるようになります。 
  
個人データの一部を新しいビジネス ID に移動する場合は、次の手順に従います。
  
## <a name="onedrive"></a>[OneDrive](#tab/OneDrive)
  
 **OneDrive データをコピーする**
1. ハード ドライブに一時フォルダーを作成して、ビジネス用に移行するファイルを一時的にMicrosoft 365します。
    
2. サブスクリプションへのアクセスに使用する Microsoft アカウントを使用して、アクセス [https://onedrive.live.com/](https://onedrive.live.com/) してサインインMicrosoft 365 Familyします。 
    
3. ビジネス用に使用するファイルMicrosoft 365手順 1 で作成したローカル フォルダーにコピーします。
    
 **ビジネスOneDriveファイルをMicrosoft 365インポートする**
1. [パスワード] [admin.microsoft.com](https://go.microsoft.com/fwlink/?LinkId=816877)に移動し、ユーザー名とパスワードMicrosoft 365 Apps for businessサインインします。 
    
2. 左上の **アプリ起動ツール** アイコンを選択し、[ **OneDrive**] を選択します。
  
    > [!TIP]
    > OneDrive for Business を初めて開いたときに、OneDrive をセットアップする必要があります。 これが発生した場合は、[ようこそ] ページ **で、[次OneDrive for Business]** を **選択します**。 セットアップOneDrive、準備が完了OneDrive **を選択します**。 
  
3. You'll be taken to an empty OneDrive folder. サブフォルダーを作成する場合は、[新しいフォルダー] **を** \> **選択します**。

4. **[アップロード]** を選択して、ファイルをコピーしたハード ドライブからファイルをOneDriveします。 
  
    > [!NOTE]
    >  個々のファイルとファイルのグループ (特定のフォルダー内のすべてのファイルなど) を同時にアップロードできますが、OneDrive for Business にフォルダーをコピーすることはできません。代わりに、OneDrive for Business に必要なフォルダー構造を作成する必要があります。 >  手順 4 で作成したフォルダーにファイルをコピーする場合は、ファイルをアップロードする前に、そのフォルダーを開きます。そうしないと、ファイルはルート フォルダーにアップロードされます。ファイルのアップロード後、OneDrive for Business のフォルダー間でファイルを移動することもできます。 
  
## <a name="outlookemail"></a>[Outlook/メール](#tab/Outlook)
  
 **Outlook 2013 の情報を Outlook データ ファイルにエクスポートする**
1. Outlook データ ファイル (.pst) を作成する前に、Outlook の情報をエクスポートするアカウントが、デスクトップ バージョンの Outlook に既に追加されている必要があります。Outlook 2013 以上にアカウントを追加する方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54)」を参照してください。
    
2. 各ユーザーは、「[メール、連絡先、予定表を Outlook の .pst ファイルにエクスポートまたはバックアップする](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)」の手順を実行する必要があります。
    
 **Outlook で新しいメール アカウントをセットアップする**
1. 各ユーザーは、ビジネス サブスクリプションのアカウントに含Microsoft 365を設定する必要があります。 これを行うには、新しいメール アカウントのアドレスが必要です。 各ユーザーの電子メール アカウントは、ビジネス向けアカウントへのサインインに使用するユーザー Microsoft 365同じです。 Sue@contoso.onmicrosoft.com や david@contoso.com のようなものになります。
    
2. 各ユーザーに、メール アカウントを Outlook に追加するように求めます。この方法については、「[Outlook 2010 または 2013 で Office 365 のメールを設定する](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b)」または「[Outlook for Mac 2011 で電子メールを設定する](https://support.microsoft.com/office/de372dc4-9648-4044-a76c-e8a60e178d54)」を参照してください。
    
 **Outlook データ ファイルから情報をインポートする**
1. これにより、PST ファイルに保存されている電子メール、予定表、タスク、連絡先がビジネス 用メール Microsoft 365に結合されます。
    
2. PST ファイルに保存されている情報をビジネス用メール アカウント用の Microsoft 365 にインポートするには、各ユーザーに、メール、連絡先、および予定表を Outlook .pst ファイルからインポートするの手順[を完了](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)します。
    
---

