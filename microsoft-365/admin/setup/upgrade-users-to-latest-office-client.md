---
title: 2010 Office 2010 を Microsoft 365 - Microsoft 365管理者にアップグレードする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 組織のユーザーの最新Microsoft OfficeクライアントOfficeアップグレードする方法について学習します。
ms.topic: article
ms.openlocfilehash: 7994fb10d00484f2c211f4443d2030fa71003d5f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321699"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>ビジネス ユーザー Microsoft 365最新のクライアントにアップグレードOfficeする

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 がサポート終了に達する

Office 2010 年 10 月 13 日にサポートが終了しました。 Microsoft は、次の情報を提供しなくなりました。

- 問題に関するテクニカル サポート

- 検出された問題のバグ修正

- 検出された脆弱性のセキュリティ修正

詳細[についてはOffice 2010 サポート終了ロードマップを](/deployoffice/endofsupport/office-2010-end-support-roadmap)参照してください。

 **これは適切なトピックですか?**
  
 組織のビジネス サブスクリプションのMicrosoft 365管理者である場合は、適切な場所にいます。 管理者は通常、ユーザーの管理、パスワードのリセット、インストールの管理、ライセンスのOffice削除など、タスクを担当します。

 管理者ではなく、[Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 製品を持っている場合は、「Office をアップグレードする方法」[](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)を参照して、古い自宅使用バージョンの Office をアップグレードします。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>アップグレードの準備を整え、Microsoft 365

管理者は、組織内のユーザーがインストールOfficeのバージョンを制御します。 Office 2010、Office 2013、Office 2016 などの古いバージョンの Office を実行している組織内のユーザーが、セキュリティと生産性の向上を活用するために最新バージョンにアップグレードすることを強くお勧めします。

## <a name="upgrade-steps"></a>アップグレード手順

以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。
  
## <a name="step-1---check-system-requirements"></a>手順 1 - システム要件の確認

[デバイスが最新バージョン](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)の Officeと互換性を持つかどうかを確認するには、デバイスのシステム要件をOffice。 たとえば、XP または Vista をOfficeしているコンピューターに新しいバージョンWindowsインストールWindowsできます。
  
> [!TIP]
> 組織内のユーザーが以前のバージョンの Windows PC またはラップトップで実行している場合は、デバイスにアップグレードすることをお勧Windows 10。 Windows 7 がサポートの終了に達しました。 詳[しくは、「7 Windows 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 年 1 月のサポート終了」をご覧ください。

オペレーティング システムを[Windows 10できる場合](https://www.microsoft.com/windows/windows-10-specifications)は、システム要件を確認してください。

### <a name="check-application-compatibility"></a>アプリケーションの互換性の確認

アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。
  
たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>手順 2 - 既存のサブスクリプション プランの確認

一部Microsoft 365プランには完全なデスクトップ バージョンの Office が含まれるので、プランに Office が含まれる場合はアップグレードの手順が異Office。
  
どのサブスクリプション プランを持っているのか分からないでしょうか。 「[ビジネス Microsoft 365のサブスクリプションに関する情報」を参照してください。](../admin-overview/what-subscription-do-i-have.md)
  
既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。
  
既存のプランに Office が含まれていない場合、下のオプションから選択してください。
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office が含まれていないプランのアップグレード オプション

 **オプション 1: サブスクリプションOffice切り替える**

Office を含むサブスクリプションに切り替えてください。 「[ビジネス プランの別のMicrosoft 365に切り替える」を参照してください](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**オプション 2: ボリューム ライセンスを通じて個別の購入、Office購入Office購入する**

 - 1 回に 1 回の購入を行う場合は、Office。 「[Office ホーム ビジネスまたは&amp;ホーム ビジネス」](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b)を[参照Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     または

 - ボリューム ライセンスを使用してOfficeコピーを購入します。 「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。

## <a name="step-3---uninstall-office"></a>手順 3 - Office をアンインストールする

最新バージョンのバージョンの Officeをインストールする前に、以前のすべてのバージョンのコンピューターをアンインストールすることをお勧Office。 ただし、Office のアップグレードに関する考え方を変更する場合は、アンインストール後にOfficeを再インストールできない次のインスタンスに注意してください。
  
サード パーティ製アドインがある場合は、製造元に問い合わせ、最新バージョンの Office で動作する更新プログラムがインストールされていないか確認することをお勧めします。

> [!TIP]
> Office のアンインストール中に問題が発生した場合は、Microsoft サポート/回復アシスタント ツールを使用して、Office: Microsoft サポート/回復アシスタント をダウンロードして[実行します](https://go.microsoft.com/fwlink/?LinkID=2155008)。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>アンインストールするバージョンの Office を選択します

- [PC から](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac から](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>以前のバージョンの Office をアンインストール後に再インストールできない既知の問題

 **Office ライセンス** を使用して削除する これらのボリューム ライセンス バージョンの Office のソース ファイルにアクセスできなくなった場合は、再インストールを行う必要はありません。

 **Officeに** プリインストールされているディスクまたはプロダクト キーがなくなった場合 (Office がインストールされている場合) は、再インストールできません。

 **サポートされていないサブスクリプション** Office のコピーが Office 365 Small Business Premium や Office 365 Mid-size Business などの廃止されたサブスクリプションを通じて入手された場合は、サブスクリプションに関連付けられているプロダクト キーがない限り、以前のバージョンの Office をインストールできます。

以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。

## <a name="step-4---assign-office-licenses-to-users"></a>手順 4 - Office ライセンスをユーザーに割り当てる

まだインストールしていない場合は、Office をインストールする必要がある組織内のユーザーにライセンスを割り当てる、「ビジネス向け Microsoft 365 ユーザーにライセンスを割[り当](../manage/assign-licenses-to-users.md)てる」を参照してください。
  
## <a name="step-5---install-office"></a>手順 5 - Office をインストールする

すべてのライセンスをアップグレードするユーザーを確認した後、最後の手順は、Office をインストールする手順です。「pc または [Mac に Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) をダウンロードしてインストールまたは再インストールする」を参照してください。
  
> [!TIP]
> ユーザーがユーザー自身でインストールしない場合は、「Officeのソフトウェアダウンロード設定の管理[」を参照Office 365](/DeployOffice/manage-software-download-settings-office-365)。 [Office 展開ツールを](/DeployOffice/overview-office-deployment-tool)使用して、Office ソフトウェアをローカル ネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用して Office を展開できます。