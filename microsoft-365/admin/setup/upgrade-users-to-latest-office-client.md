---
title: Office 2010 を Microsoft 365 にアップグレードする - Microsoft 365管理者
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
description: 組織内のユーザーのMicrosoft Officeを最新のOffice クライアントにアップグレードする方法について説明します。
ms.topic: article
ms.openlocfilehash: 7994fb10d00484f2c211f4443d2030fa71003d5f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321699"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>ビジネス ユーザーのMicrosoft 365を最新のOffice クライアントにアップグレードする

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 がサポート終了に達する

Office 2010 は、2020 年 10 月 13 日にサポートの終了に達しました。 Microsoft では、次の情報は提供されなくなりました。

- 問題のテクニカル サポート

- 検出された問題のバグ修正

- 検出された脆弱性のセキュリティ修正プログラム

詳細については[、Office 2010 のサポート終了ロードマップ](/deployoffice/endofsupport/office-2010-end-support-roadmap)を参照してください。

 **これは適切なトピックですか?**
  
 組織内のビジネス サブスクリプションのMicrosoft 365を担当する管理者は、適切な場所にいます。 管理者は通常、ユーザーの管理、パスワードのリセット、Officeインストールの管理、ライセンスの追加または削除などのタスクを担当します。

 管理者ではなく、[Microsoft 365 Family](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans)製品をお持ちでない場合は、古い自宅使用バージョン[のOfficeのアップグレード](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)の詳細については、「操作方法アップグレード Office」を参照してください。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Microsoft 365にアップグレードする準備をする

管理者は、組織内のユーザーがインストールできるOfficeのバージョンを制御します。 Office 2010、Office 2013、Office 2016 など、古いバージョンのOfficeを実行している組織内のユーザーが、セキュリティと生産性の向上を利用できるように、最新バージョンにアップグレードすることを強くお勧めします。

## <a name="upgrade-steps"></a>アップグレード手順

以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。
  
## <a name="step-1---check-system-requirements"></a>手順 1 - システム要件の確認

Office[のシステム要件を確認](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources)して、デバイスが最新バージョンのOfficeと互換性があることを確認します。 たとえば、XP または Windows Vista を実行しているコンピューターには、新しいバージョンのOffice Windowsインストールできません。
  
> [!TIP]
> 組織内のユーザーが PC またはノート PC で古いバージョンのWindowsを実行している場合は、Windows 10にアップグレードすることをお勧めします。 Windows 7 がサポートの終了に達しました。 詳細[については、Windows 7 のサポートは 2020 年 1 月に終了](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)します。

[Windows 10システム要件](https://www.microsoft.com/windows/windows-10-specifications)を確認して、オペレーティング システムをアップグレードできるかどうかを確認します。

### <a name="check-application-compatibility"></a>アプリケーションの互換性の確認

アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。
  
たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>手順 2 - 既存のサブスクリプション プランの確認

一部のMicrosoft 365プランには、Officeの完全なデスクトップ バージョンが含まれていません。プランにOfficeが含まれていない場合、アップグレードする手順は異なります。
  
どのサブスクリプション プランを持っているかが不明ですか? [ビジネス サブスクリプションのMicrosoft 365](../admin-overview/what-subscription-do-i-have.md)を確認してください。
  
既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。
  
既存のプランに Office が含まれていない場合、下のオプションから選択してください。
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office が含まれていないプランのアップグレード オプション

 **オプション 1: サブスクリプションOffice切り替える**

Office を含むサブスクリプションに切り替えてください。 [ビジネス プランの別のMicrosoft 365に切り替える方法に関するガイドを](../../commerce/subscriptions/switch-to-a-different-plan.md)参照してください。

**オプション 2: 個人の購入、Officeの 1 回限りの購入、またはボリューム ライセンスを使用したOfficeの購入**

 - Officeの個別の 1 回限りの購入を購入します。 [ホーム &amp; ビジネスまたはOffice Professional Office](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b)を参照してください[](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     または

 - ボリューム ライセンスを使用して、Officeの複数のコピーを購入します。 「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。

## <a name="step-3---uninstall-office"></a>手順 3 - Office をアンインストールする

最新バージョンのOfficeをインストールする前に、古いバージョンのOfficeをすべてアンインストールすることをお勧めします。 ただし、Officeのアップグレードに関する考えを変更した場合は、アンインストール後にOfficeを再インストールできない次のインスタンスに注意してください。
  
サードパーティのアドインがある場合は、製造元に問い合わせて、最新バージョンのOfficeで動作する更新プログラムがあるかどうかを確認することをお勧めします。

> [!TIP]
> Officeのアンインストール中に問題が発生した場合は、Microsoft サポートおよび回復アシスタント ツールを使用してOfficeを削除できます。[Microsoft サポートと回復アシスタントをダウンロードして実行](https://go.microsoft.com/fwlink/?LinkID=2155008)します。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>アンインストールするバージョンの Office を選択します

- [PC から](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac から](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>以前のバージョンの Office をアンインストール後に再インストールできない既知の問題

 **ボリューム ライセンスを使用してOffice** これらのボリューム ライセンス バージョンのOfficeのソース ファイルにアクセスできなくなった場合は、再インストールできません。

 **Officeコンピューターに事前インストールされている** ディスクキーまたはプロダクト キーがなくなった場合 (Office付属している場合)、再インストールできません。

 **サポートされていないサブスクリプション** Officeのコピーが、Office 365 Small Business PremiumやOffice 365 Mid-size Business などの廃止されたサブスクリプションを通じて取得された場合、サブスクリプションに付属するプロダクト キーがない限り、古いバージョンのOfficeをインストールすることはできません。

以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。

## <a name="step-4---assign-office-licenses-to-users"></a>手順 4 - Office ライセンスをユーザーに割り当てる

まだインストールしていない場合は、Officeをインストールする必要がある組織内のユーザーに[ライセンスを割り当てる方法については、「ビジネス向けのMicrosoft 365のユーザーにライセンスを割り当てる」を](../manage/assign-licenses-to-users.md)参照してください。
  
## <a name="step-5---install-office"></a>手順 5 - Office をインストールする

すべてのライセンスをアップグレードするユーザーがライセンスを持っていることを確認したら、最後の手順として、Officeをインストールし、[PC または Mac にOfficeをダウンロードしてインストールまたは再インストールする方法に関するページを](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)参照してください。
  
> [!TIP]
> ユーザーが自分でインストールOfficeしたくない場合は、「[Office 365でソフトウェアのダウンロード設定を管理](/DeployOffice/manage-software-download-settings-office-365)する」を参照してください。 [Office展開ツール](/DeployOffice/overview-office-deployment-tool)を使用して、Office ソフトウェアをローカル ネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用してOfficeを展開できます。