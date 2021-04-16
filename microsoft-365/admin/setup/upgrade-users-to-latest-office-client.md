---
title: 2010 Office Microsoft 365 にアップグレードする - Microsoft 365 管理者
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: 3d2d5e54506d06662c6c2feef0d142f1e195163f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860573"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>ビジネス ユーザー向け Microsoft 365 を最新のクライアントにOfficeする

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 がサポートの終了に達する

Office 2010 年 10 月 13 日にサポートが終了しました。 Microsoft は、次の情報を提供しなくなりました。

- 問題に関するテクニカル サポート

- 検出された問題のバグ修正

- 検出された脆弱性のセキュリティ修正

詳細 [についてはOffice 2010 サポート終了ロードマップを](/deployoffice/endofsupport/office-2010-end-support-roadmap) 参照してください。

 **これは適切なトピックですか?**
  
 組織の Microsoft 365 for business サブスクリプションの管理者である場合は、適切な場所にいます。 管理者は通常、ユーザーの管理、パスワードのリセット、インストールの管理、ライセンスOfficeまたは削除するタスクを担当します。

 [管理者ではなく、Microsoft 365 ファミリ](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans)製品を使用している場合は、「Office[](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)をアップグレードする方法」を参照して、古い自宅使用バージョンの Office をアップグレードします。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Microsoft 365 にアップグレードする準備をする

管理者は、組織内のユーザーがインストールOfficeバージョンを制御します。 Office 2010、Office 2013、Office 2016 などの古いバージョンの Office を実行している組織内のユーザーが、セキュリティと生産性の向上を活用するために最新バージョンにアップグレードすることを強くお勧めします。

## <a name="upgrade-steps"></a>アップグレード手順

以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。
  
## <a name="step-1---check-system-requirements"></a>手順 1 - システム要件の確認

[デバイスが最新バージョン](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) のOffice互換性を持つかどうかを確認するには、デバイスのシステム要件を確認Office。 たとえば、新しいバージョンOffice Windows XP または Windows Vista を実行しているコンピューターにインストールできない場合です。
  
> [!TIP]
> 組織内のユーザーが PC またはラップトップで以前のバージョンの Windows を実行している場合は、Windows 10 にアップグレードすることをお勧めします。 Windows 7 はサポートの終了に達しました。 詳細 [については、「Windows 7 のサポートは 2020 年 1](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 月に終了します」を参照してください。

[Windows 10 のシステム要件を](https://www.microsoft.com/windows/windows-10-specifications)確認して、オペレーティング システムをアップグレードできる場合を確認します。

### <a name="check-application-compatibility"></a>アプリケーションの互換性の確認

アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。
  
たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>手順 2 - 既存のサブスクリプション プランの確認

一部の Microsoft 365 プランには、Office の完全なデスクトップ バージョンが含まれるので、プランに Office が含まれる場合はアップグレード手順が異なります。
  
どのサブスクリプション プランを持っているのか分からないでしょうか。 「Microsoft [365 for business サブスクリプションに関する情報」を参照してください。](../admin-overview/what-subscription-do-i-have.md)
  
既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。
  
既存のプランに Office が含まれていない場合、下のオプションから選択してください。
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office が含まれていないプランのアップグレード オプション

 **オプション 1: サブスクリプションOffice切り替える**

Office を含むサブスクリプションに切り替えてください。 「 [ビジネス プラン用に別の Microsoft 365 に切り替える」を参照してください](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**オプション 2: ボリューム ライセンスを通じて個別の購入、Office購入、Office購入**

 - 1 回に 1 回の購入を行う場合は、Office。 「Office [ビジネス &amp; またはプロフェッショナル](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) 」 [をOfficeする](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     または

 - ボリューム ライセンスを使用して、Officeコピーを複数購入します。 「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。

## <a name="step-3---uninstall-office"></a>手順 3 - Office をアンインストールする

最新バージョンのバージョンをインストールする前Office、古いバージョンのすべてのバージョンのコンピューターをアンインストールすることをお勧Office。 ただし、Office のアップグレードに関する考え方を変更した場合は、アンインストール後に Officeを再インストールできない場合に注意してください。
  
サード パーティ製のアドインがある場合は、製造元に問い合わせ、最新バージョンの Office で動作する更新プログラムが含Office。

> [!TIP]
> Office のアンインストール中に問題が発生した場合は、Microsoft サポート と回復アシスタント ツールを使用して、Office: [Microsoft](https://go.microsoft.com/fwlink/?LinkID=2155008)サポート と回復アシスタントをダウンロードして実行します。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>アンインストールするバージョンの Office を選択します

- [PC から](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac から](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>以前のバージョンの Office をアンインストール後に再インストールできない既知の問題

 **Office ライセンスを使用して管理する** これらのボリューム ライセンス バージョンの Office ソース ファイルにアクセスできなくなった場合は、再インストールを行う必要はありません。

 **Officeに事前にインストールされている場合** ディスクまたはプロダクト キーがなくなった場合 (Officeがインストールされている場合) は、再インストールを行う必要はありません。

 **サポートされていないサブスクリプション** Office のコピーが、Office 365 Small Business Premium や Office 365 Mid-size Business などの廃止されたサブスクリプションを通じて入手された場合、サブスクリプションに含められるプロダクト キーがない限り、Office の古いバージョンをインストールできない。

以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。

## <a name="step-4---assign-office-licenses-to-users"></a>手順 4 - Office ライセンスをユーザーに割り当てる

まだインストールしていない場合は、Office をインストールする必要がある組織内のユーザーにライセンスを割り当てる、「ビジネス向け [Microsoft 365](../manage/assign-licenses-to-users.md)のユーザーにライセンスを割り当てる」を参照してください。
  
## <a name="step-5---install-office"></a>手順 5 - Office をインストールする

すべてのライセンスをアップグレードするユーザーを確認した後、最後に、Office をインストールし [、PC](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)または Mac に Office をダウンロードしてインストールまたは再インストールするを参照してください。
  
> [!TIP]
> ユーザーが自分でインストールしない場合は、「Office [365](/DeployOffice/manage-software-download-settings-office-365)でのソフトウェアダウンロード設定の管理」を参照Officeしてください。 Office 展開ツール [を](/DeployOffice/overview-office-deployment-tool) 使用して、Office ソフトウェアをローカル ネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用Officeを展開できます。