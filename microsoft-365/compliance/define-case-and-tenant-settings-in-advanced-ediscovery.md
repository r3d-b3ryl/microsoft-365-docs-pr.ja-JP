---
title: Advanced eDiscovery でケースとテナントの設定を定義する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 383809de-7f5e-4a1d-9098-c525f67b7a9a
description: Advanced eDiscovery のケース レベルで定義できるラベル、クロス モジュール、テナント設定について説明します。
ms.openlocfilehash: e2f46a9339e2c134be505138aac6886cb1a2dd9a
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663052"
---
# <a name="define-case-and-tenant-settings-in-advanced-ediscovery-classic"></a>Advanced eDiscovery (クラシック) でケースとテナントの設定を定義する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
このトピックでは、Advanced eDiscovery のケースとテナントの設定について説明します。
  
## <a name="case-settings"></a>ケースの設定

このセクションでは、ケース レベルで定義できる設定について説明します。
  
> [!NOTE]
> Advanced eDiscovery で現在選択されているケースがない場合、[ **ケースの設定** ] タブは非アクティブです。 
  
### <a name="cross-module"></a>クロス モジュール

次のクロス モジュール設定は、Advanced eDiscovery モジュールに適用されるケース オプションです。
  
- ログイン後の既定のページ: Advanced eDiscovery の起動時に表示される既定のページを設定します。
    
- ファイル表示名: Advanced eDiscovery 全体でファイルを識別するために、ファイルタイトル/パスまたは電子メールの件名の Advanced eDiscovery 表示名の代わりに表示されるファイル識別子。
    
1. [ **ホイール] アイコンをクリック** して、[設定とユーティリティ **] を開** きます。 Open **Settings and utilities Case \> settings** tab \> **Cross module**. 
    
2. ログイン後の既定 **のページから選択** します。 
    
  - **以前のログインの最後のページ**
    
  - **ケース ページ**
    
3. **[保存]** をクリックします。
    
## <a name="tenant-settings"></a>テナントの設定

Advanced eDiscovery テナントの設定については、このセクションで説明します。
  
### <a name="user-administration"></a>ユーザー管理

ユーザー管理オプションについては、「ユーザーとケース [の設定」を参照してください](set-up-users-and-cases-in-advanced-ediscovery.md)。
  
### <a name="event-log"></a>イベント ログ

イベント ログは、Advanced eDiscovery 操作中の Advanced eDiscovery 処理に関するメタデータを提供します。 たとえば、主要な Advanced eDiscovery プロセス (インポート、分析、関連性、エクスポート) の開始時刻と、終了時刻と状態が含まれます。 このログは、データ処理アクティビティの追跡とトラブルシューティング、およびエラーや警告への対処に使用できます。
  
1. [ **ホイール] アイコンをクリック** して、[設定とユーティリティ **] を開** きます。 
    
2. [設定と **ユーティリティのテナント設定 \> ] タブで** 、[イベント ログ] **を選択します**。 イベント ログ データが表示されます。
    
  - ケースによってログ出力をフィルター処理するには、[ケース] の一覧からケース **を選択** します。 
    
  - ログを列で並べ替える場合は、列ヘッダーをクリックします。 
    
  - 列の順序を変更するには、列ヘッダーをクリックしてドラッグします。
    
  - ログ ページ間を移動するには、クリックと **\>** アイコン **\<** をクリックします。 
    
### <a name="system-information"></a>システム情報

Advanced eDiscovery version system information and active tasks are displayed in the Tenant settings tab.
  
1. [ **ホイール] アイコンをクリック** して、[設定とユーティリティ **] を開** きます。 
    
2. [設定と **ユーティリティのテナント設定 \> ] タブで** 、[システム情報] **を選択します**。 バージョン情報が表示されます。
    
表示を更新するには、テナント情報の下にある[更新] アイコンをクリックします。 
  
## <a name="see-also"></a>関連項目

[Advanced eDiscovery (クラシック)](office-365-advanced-ediscovery.md)
  
[ユーティリティの使用](use-advanced-ediscovery-utilities.md)

