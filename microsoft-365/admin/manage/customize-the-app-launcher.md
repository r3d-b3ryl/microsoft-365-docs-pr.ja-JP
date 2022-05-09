---
title: カスタム タイルをアプリ起動ツールに追加する
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: カスタム タイルをアプリ起動ツールに追加して、メール、ドキュメント、アプリ、SharePoint サイト、外部サイト、その他のリソースへのクイック リンクを作成します。
ms.openlocfilehash: 31121df0e1af6b8fc2be1e61ba7e0cd0714affa2
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464021"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>カスタム タイルをアプリ起動ツールに追加する

Microsoft 365では、アプリ起動ツールを使用して、メール、予定表、ドキュメント、アプリにすばやく簡単にアクセスできます ([詳細については、こちらを参照してください](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a))。 これらは、Microsoft 365で取得するアプリと、[SharePoint ストア](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43)または[Azure AD](/previous-versions/office/office-365-api/)から追加するカスタム アプリです。
  
SharePoint サイト、外部サイト、レガシー アプリなどをポイントするカスタム タイルをアプリ起動ツールに追加できます。カスタム タイルは、アプリ起動ツールの [ **すべて**] のアプリの下に表示されますが、[ **ホーム**] アプリにピン留めしたり、同じ操作を行うようにユーザーに指示したりできます。この操作により、関連サイト、アプリ、仕事に必要なリソースへのアクセスが容易になります。以下の例では、"Contoso Portal" と呼ばれるカスタム タイルを使って、組織の SharePoint イントラネット サイトにアクセスします。 
  
![アプリ起動ツール。](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>カスタム タイルをアプリ起動ツールに追加する

1. 全体管理者として管理センターにサインインし、**設定** > **Org 設定** に移動して、[**組織プロファイル**] タブを選択します。
    
2. [ **組織プロファイル** ] タブで、[ **カスタム アプリ起動ツール タイル**] を選択します。
  
3. [ **カスタム タイルの追加] を選択します**。 
  
4. 新しいタイルの **タイル名** を入力します。名前がタイルに表示されます。 
    
5. タイル **の Web サイトの URL を** 入力します。 これは、アプリ起動ツールでタイルを選択したときにユーザーが移動する場所です。 URL で HTTPS を使用します。

    > [!TIP]
    > SharePoint サイト用のタイルを作成する場合、そのサイトへ移動し、URL をコピーし、ここに貼り付けてください。 既定のチーム サイトの URL は次のようになります。 `https://<company_name>.sharepoint.com` 
  
6. タイル **の画像の URL を** 入力します。 この画像は [個人用アプリ] ページとアプリ起動ツールに表示されます。

    > [!TIP]
    > イメージは 60 x 60 ピクセルで、認証を必要とせずに組織内のすべてのユーザーが使用できるようにする必要があります。

7. タイルの **説明** を入力します。 これは、[マイ アプリ] ページでタイルを選択し、[ **アプリの詳細**] を選択すると表示されます。 
  
8. [ **変更の保存] を** 選択して、カスタム タイルを作成します。 
    
    カスタム タイルは、今後 24 時間以内にアプリ起動ツールの [ **すべて** ] タブに表示され、ユーザーとユーザーが表示されます。 

    > [!NOTE]
    > 前の手順で作成したカスタム タイルが表示されない場合は、Exchange Online メールボックスが自分に割り当てられていること、およびメールボックスに最低一度はサインインしていることを確認します。 これらの手順は、Microsoft 365のカスタム タイルに必要です。 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. 管理センターで、**設定** > **Org 設定** > **Organization プロファイル** タブに移動します。
    
2. **[組織プロファイル**] ページで、[**カスタム アプリ起動ツール] タイル** に移動します。[**カスタム タイル**] の横にある 3 つのドットを選択し、[**カスタム タイルの編集**] を選択します。

3. カスタム タイルの **タイル名**、 **URL**、 **説明**、 **画像 URL** を更新します。( [カスタム タイルをアプリ起動ツールに追加する](#add-a-custom-tile-to-the-app-launcher)参照)。
    
4. [**Update Close**] (**更新プログラム** の終了) \> を選択します。 
    
カスタム タイルを削除するには、[**カスタム タイル**] ウィンドウでタイルを選択し、**tileDelete** >  の **削除** を選択します。 
  
## <a name="next-steps"></a>次の手順

 組織のブランドに合わせてMicrosoft 365の外観をカスタマイズするには、「[Microsoft 365テーマをカスタマイズする](../setup/customize-your-organization-theme.md)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[アプリをユーザーのアプリ起動ツールにピン留め](pin-apps-to-app-launcher.md) する (記事)\
[ビジネス ユーザーのMicrosoft 365を最新のOffice クライアントにアップグレードする](../setup/upgrade-users-to-latest-office-client.md) (記事)\
[管理センターでアドインを管理する](../manage/manage-addins-in-the-admin-center.md) (記事)
