---
title: SharePoint 管理センターにおける Information Rights Management (IRM) の設定
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Microsoft Azure Active Directory Rights Management サービス (RMS) を通じて SharePoint Online IRM を使用し、SharePoint リストやドキュメント ライブラリを保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f40977e453b228eddc745a6d29e3f5d119276abe
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170597"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>SharePoint 管理センターにおける Information Rights Management (IRM) の設定

SharePoint Online では、リストおよびライブラリのレベルでファイルに IRM 保護が適用されます。 組織で IRM 保護を使用するには、まず、Rights Management をセットアップしておく必要があります。 IRM は Azure Information Protection の Azure Rights Management サービスを利用して、暗号化と使用制限の割り当てを実施します。 Microsoft 365 のプランには Azure Rights Management が含まれているものと、含まれていないものがあります。 詳細については、「[Office のアプリケーションとサービスが Azure Rights Management をサポートするしくみ](/azure/information-protection/understand-explore/office-apps-services-support)」を参照してください。
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>SharePoint 管理センターを使って IRM サービスを有効にする

組織で SharePoint リストとライブラリを IRM で保護するには、最初に Rights Management サービスを組織向けにアクティブにする必要があります。 手順については、「[Azure Rights Management をアクティブにする](/information-protection/deploy-use/activate-service)」をご覧ください。 Rights Management サービスを有効にするには、グローバル管理者権限を持つ職場または学校アカウントを使用する必要があります。 そうしないと、SharePoint Online で IRM 機能を使用できなくなります。
  
Rights Management サービスをアクティブにしたら、SharePoint 管理センターにサインインして、IRM をオンにします。
  
1. グローバル管理者または SharePoint 管理者としてサインインします。
    
2. [アプリ起動ツール] アイコン ![ [アプリ起動ツール] アイコンを選択Office 365。](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) をクリックし、[**管理者**] を選択して、Microsoft 365 管理センター。 ([管理者] タイルが表示されない場合、組織の管理者のアクセス許可が付与されていません。) 
    
3. 左側のウィンドウで、**[管理センター]** \> **[SharePoint]** の順に選択します。
    
4. 左側のウィンドウで、**[設定]** を選択してから、**[クラシック設定] ページ** を選択します。
    
5. **[Information Rights Management (IRM)]** セクションで、**[構成で指定した IRM サービスを使う]**、**[IRM 設定の更新]** の順に選びます。 IRM 設定を更新したら、組織内のユーザーは SharePoint リストとドキュメント ライブラリで IRM の使用を開始できます。 ただし、そのためのオプションが [ライブラリ設定] と [リスト設定] に表示されるまでに最大 1 時間かかる場合があります。
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM 対応の SharePoint ドキュメント ライブラリとリスト
<a name="__toc220831191"> </a>

IRM 設定を更新したら、サイト所有者は SharePoint リストとドキュメント ライブラリを IRM で保護できます。 詳細については、「[Information Rights Management をリストまたはライブラリに適用する](apply-irm-to-a-list-or-library.md)」を参照してください。
  
サイト所有者がリストまたはライブラリに対して IRM を有効にすると、そのリストまたはライブラリでサポートされているファイルの種類を保護できます。 ライブラリで IRM が有効になっている場合、著作権管理はそのライブラリ内のすべてのファイルに適用されます。 リストに対して IRM を有効にすると、実際のリスト アイテムではなくリスト アイテムに関連付けられたファイルだけに著作権管理が適用されます。
  
ユーザーが IRM 対応のリストまたはライブラリ内のファイルをダウンロードすると、ファイルは暗号化されるため、許可されたユーザーのみがファイルを表示できます。 権限が管理されたファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスも含まれています。 一般的な制限には、ファイルを読み取り専用にする、テキストのコピーを無効にする、ユーザーがローカル コピーを保存できないようにする、ユーザーがファイルを印刷できないようにするなどがあります。 IRM でサポートされているファイルの種類を読み取ることができるクライアント プログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。 これは、権限が管理されたファイルがダウンロードされた後でもその保護を維持する方法です。 リストまたはライブラリで IRM を有効にするには、「[Information Rights Management をリストまたはライブラリに適用する](apply-irm-to-a-list-or-library.md)」を参照してください。
  
ブラウザーで Office を使用して、IRM 対応ライブラリでドキュメントを作成または編集することはできません。 代わりに、1 人ずつ IRM 暗号化ファイルをダウンロードして編集できます。 チェックインとチェックアウトを使用して、*共同編集*、または複数のユーザー間での作成を管理します。 
  
IRM で保護されたライブラリから PDF ファイルをダウンロードすると、Microsoft 365 は保護された PDF ファイルを作成します。 ファイルの拡張子は変更されませんが、ファイルは保護されます。 このファイルを表示するには、Azure Information Protection ビューアー、完全な Azure Information Protection クライアント、または保護された PDF ファイルの表示をサポートする別のアプリケーションが必要です。 
  
SharePoint Online は次のファイルの種類の暗号化をサポートします。
  
- PDF
    
- Microsoft Office Word、Microsoft Office Excel、Microsoft Office PowerPoint の 97 から 2003 までのファイル形式
    
- Microsoft Office Word、Microsoft Office Excel、および Microsoft Office PowerPoint の Office Open XML 形式
    
- XML Paper Specification (XPS) 形式
 
> [!NOTE]
> SharePoint はアップロード時にドキュメントを開く必要があるため、保護されたドキュメント (デジタル署名の PDF ファイルなど) に IRM 保護を適用することはできません。 

## <a name="next-steps"></a>次の手順
<a name="__toc220831191"> </a>

SharePoint Online の IRM を有効にすると、リストとライブラリへの著作権管理の適用を開始できます。 詳細については、「[Information Rights Management をリストまたはライブラリに適用する](apply-irm-to-a-list-or-library.md)」を参照してください。
  
Windows の新しい OneDrive 同期クライアントでは、(ライブラリの IRM 設定に、ドキュメントのアクセス権の期限が設定されていない限り) IRM で保護された SharePoint ドキュメント ライブラリと OneDrive の場所の同期がサポートされるようになりました。 詳細について、または新しい同期クライアントの展開を開始するには、「[Windows 向けの新しい OneDrive 同期クライアントを展開する](/onedrive/deploy-on-windows)」を参照してください。
  
[ページのトップへ](set-up-irm-in-sp-admin-center.md)