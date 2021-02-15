---
title: Office 2010 を Microsoft 365 にアップグレードする - Microsoft 365 管理者
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
description: 組織内のユーザーの最新の Microsoft Office クライアントにOfficeする方法について学習します。
ms.openlocfilehash: 3f8ea0d16e1c27414b5f3e11e842e336fadb3e75
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233320"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>ビジネス ユーザー向け Microsoft 365 を最新のクライアントにOfficeする

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 がサポート終了に達する

Office 2010 年 10 月 13 日にサポートが終了しました。 Microsoft は、次の機能を提供しなくなりました。

- 問題に対するテクニカル サポート

- 検出された問題のバグ修正

- 検出された脆弱性に対するセキュリティ修正プログラム

詳細 [Office 2010 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) を参照してください。

 **これが適切なトピックですか?**
  
 組織の Microsoft 365 for business サブスクリプションの管理者が適切な場所にいます。 管理者は、通常、ユーザーの管理、パスワードのリセット、Officeインストールの管理、ライセンスの追加または削除など、タスクを担当します。

 管理者ではなく[、Microsoft 365 ファミリ](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans)製品をお持ちのお客様は、「Office[](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350)をアップグレードする方法」を参照して、以前の自宅使用バージョンの Office をアップグレードしてください。

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Microsoft 365 にアップグレードする準備をする

管理者は、組織内のユーザーがインストールOfficeバージョンを制御します。 Office 2010、Office 2013、Office 2016 など、以前のバージョンの Office を実行している組織内のユーザーが最新バージョンにアップグレードし、セキュリティと生産性の向上を活用することを強くお勧めします。

## <a name="upgrade-steps"></a>アップグレード手順

以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。
  
## <a name="step-1---check-system-requirements"></a>手順 1 - システム要件の確認

[デバイスが最新バージョン](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) の Office互換性を持つかどうかを確認するには、デバイスのシステム要件を確認Office。 たとえば、新しいバージョンのOffice Windows XP または Windows Vista を実行しているコンピューターにインストールできない場合があります。
  
> [!TIP]
> 組織内のユーザーが PC またはノート PC で以前のバージョンの Windows を実行している場合は、Windows 10 にアップグレードすることをお勧めします。 Windows 7 のサポートが終了しました。 詳 [しくは、2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 年 1 月に終了する Windows 7 のサポートをご覧ください。

オペレーティング システムを [アップグレードできる場合は、Windows 10](https://www.microsoft.com/windows/windows-10-specifications) のシステム要件を確認してください。

### <a name="check-application-compatibility"></a>アプリケーションの互換性の確認

アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。
  
たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>手順 2 - 既存のサブスクリプション プランの確認

一部の Microsoft 365 プランにはデスクトップ版の Office が含まれますが、プランに Office が含されていない場合は、アップグレードの手順が異なります。
  
使用しているサブスクリプション プランが分からないか。 Microsoft [365 for Business サブスクリプションの内容を確認する](../admin-overview/what-subscription-do-i-have.md)
  
既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。
  
既存のプランに Office が含まれていない場合、下のオプションから選択してください。
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office が含まれていないプランのアップグレード オプション

 **オプション 1: サブスクリプションOffice切り替える**

Office を含むサブスクリプションに切り替えてください。 「 [別のビジネス向け Microsoft 365 プランに切り替える」を参照してください](../../commerce/subscriptions/switch-to-a-different-plan.md)。

**オプション 2: ボリューム ライセンスを通じて、1 回の個別Office購入Office購入する**

 - アプリの個別の 1 回の購入Office。 「Office [Home &amp; Business](https://products.office.com/home-and-business) または [Office Professional」を参照](https://products.office.com/professional)

     または

 - ボリューム ライセンスで複数のOfficeを購入します。 「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。

## <a name="step-3---uninstall-office"></a>手順 3 - Office をアンインストールする

最新バージョンの Office をインストールする前に、すべての古いバージョンのファイルをアンインストールすることをお勧Office。 ただし、Office のアップグレードに関する考え方が変わる場合は、アンインストール後にOfficeを再インストールできない場合に注意してください。
  
サード パーティ製アドインがある場合は、製造元に問い合わせ、最新バージョンの Office で動作する更新プログラムがインストールされていないか確認することをお勧めします。

> [!TIP]
> Office のアンインストール中に問題が発生した場合は、Microsoft サポート/回復アシスタント ツールを使用して Office の削除を支援できます [:Microsoft](https://go.microsoft.com/fwlink/?LinkID=2155008)サポート/回復アシスタントをダウンロードして実行します。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>アンインストールするバージョンの Office を選択します

- [PC から](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac から](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>以前のバージョンの Office をアンインストール後に再インストールできない既知の問題

 **Officeライセンスを通じてライセンスを取得する** これらのボリューム ライセンス バージョンの Office のソース ファイルにアクセスできなくなった場合は、再インストールを行う必要があります。

 **Officeコンピューターにプレインストールされている場合** ディスクまたはプロダクト キーがなくなった場合 (Officeにインストールされている場合)、再インストールは行えなくなりました。

 **サポートされていないサブスクリプション** Office のコピーが、Office 365 Small Business Premium や Office 365 Mid-size Business などの廃止されたサブスクリプションを通じて取得された場合、サブスクリプションに付けられているプロダクト キーがない限り、古いバージョンの Office をインストールできない可能性があります。

以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。

## <a name="step-4---assign-office-licenses-to-users"></a>手順 4 - Office ライセンスをユーザーに割り当てる

まだライセンスを割り当てていない場合は、Office をインストールする必要がある組織内のユーザーにライセンスを割り当てる方法について詳しくは [、「Microsoft 365 for business](../manage/assign-licenses-to-users.md)でライセンスをユーザーに割り当てる」をご覧ください。
  
## <a name="step-5---install-office"></a>手順 5 - Office をインストールする

すべてのライセンスを持つユーザーをアップグレードすることを確認した後、最後の手順として、ユーザーに Office をインストールします [。「PC](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)または Mac に Office をダウンロードしてインストールまたは再インストールする」を参照してください。
  
> [!TIP]
> ユーザーが自分でインストールする必要Office、Office [365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)でソフトウェアダウンロード設定を管理するを参照してください。 [Office](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool)展開ツールを使用して Office ソフトウェアをローカル ネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用して Office を展開できます。
