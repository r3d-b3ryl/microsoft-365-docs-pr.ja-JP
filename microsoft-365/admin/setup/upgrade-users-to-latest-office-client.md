---
title: Microsoft 365 for business ユーザーを最新の Office クライアントにアップグレードする
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
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: ユーザーを最新の Office クライアントにアップグレードする方法について説明します。
ms.openlocfilehash: 7cddf1554a5892ddac510fc77238529194c1a2a0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545730"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Microsoft 365 for business ユーザーを最新の Office クライアントにアップグレードする

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 がサポート終了に到達した

Office 2010 は、2020年10月13日にサポート終了日に到達します。 Office 2010 がサポートの終了に達すると、Microsoft は次のものを提供しなくなります。

- 問題のテクニカルサポート

- 検出された問題に対するバグ修正

- 検出された脆弱性に対するセキュリティ修正プログラム

詳細については、「 [Office 2010 のサポート終了ロードマップ](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) 」を参照してください。

 **これは適切なトピックですか。**
  
 お客様が組織の Microsoft 365 for business サブスクリプションを担当する管理者である場合は、適切な場所に配置されています。 通常、管理者は、ユーザーの管理、パスワードのリセット、Office のインストールの管理、ライセンスの追加または削除などのタスクを担当します。

 管理者ではなく、 [Microsoft 365 ファミリ](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 製品を使用している場合は、「office をアップグレードする方法について」を参照してください。以前のバージョンの office をアップグレードする方法については、「office の [アップグレード方法](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) 」を参照してください。

## <a name="get-ready-to-upgrade"></a>アップグレードの準備をする

管理者は、組織内のどのバージョンの Office ユーザーがインストールできるかを制御します。 Office 2010、Office 2013、または Office 2016 を最新バージョンにアップグレードするなど、以前のバージョンの Office を実行している組織内のユーザーが、セキュリティと生産性の向上を活かすことができるようにすることを強くお勧めします。

## <a name="upgrade-steps"></a>アップグレード手順

以下は、ユーザーが最新の Office デスクトップ クライアントにアップグレードするときのプロセスできます。アップグレード プロセスを開始する前に一読することをお勧めします。
  
## <a name="step-1---check-system-requirements"></a>手順 1 - システム要件の確認

Office の[システム要件をチェック](https://products.office.com/office-system-requirements)して、デバイスが最新バージョンの office と互換性があることを確認してください。 たとえば、Windows XP または Windows Vista を実行しているコンピューターに新しいバージョンの Office をインストールすることはできません。
  
> [!TIP]
> 組織内のユーザーが Pc またはラップトップで以前のバージョンの Windows を実行している場合は、Windows 10 にアップグレードすることをお勧めします。 Windows 7 のサポートが終了しました。 詳細については、「 [2020 年1月の Windows 7 のサポート」](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) を参照してください。

オペレーティングシステムをアップグレードできるかどうかを確認するには、 [Windows 10 のシステム要件](https://www.microsoft.com/windows/windows-10-specifications) を確認してください。

### <a name="check-application-compatibility"></a>アプリケーションの互換性の確認

アップグレードを成功させるためには、VBA スクリプト、マクロ、サードパーティ アドイン、複雑な文書とスプレッドシートなど、Office のアプリケーションと最新版の Office との間に互換性があることを確認することが推奨されます。
  
たとえば、現在インストールしている Office でサードパーティ アドインを利用している場合、最新版の Office に対応していることをメーカーにご確認ください。
  
## <a name="step-2---check-your-existing-subscription-plan"></a>手順 2 - 既存のサブスクリプション プランの確認

一部の Microsoft 365 プランには、デスクトップ版の完全な Office は含まれていません。また、アップグレードの手順は、プランに Office が含まれていない場合には異なります。
  
必要なサブスクリプションプランがわからない場合 所有して[いる Microsoft 365 for business サブスクリプションを](../admin-overview/what-subscription-do-i-have.md)参照してください。
  
既存のプランに Office が含まれる場合、「[手順 3 - Office をアンインストールする](#step-3---uninstall-office)」に移動してください。
  
既存のプランに Office が含まれていない場合、下のオプションから選択してください。
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office が含まれていないプランのアップグレード オプション

 **オプション 1: Office サブスクリプションを切り替える**

Office を含むサブスクリプションに切り替えてください。 「 [別の Microsoft 365 for business プランへの切り替え」を](../../commerce/subscriptions/switch-to-a-different-plan.md)参照してください。

**オプション 2: 個人または1回の Office の購入を購入するか、ボリュームライセンスを使用して Office を購入する**

 - Office の個別の1回の購入を購入します。 「 [Office Home &amp; Business](https://products.office.com/home-and-business)または[office Professional](https://products.office.com/professional) 」を参照してください。

     OR

 - ボリュームライセンスを使用して、Office の複数のコピーを購入します。 「[ボリューム ライセンスで提供されるスイート製品の比較](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)」をご覧ください。

## <a name="step-3---uninstall-office"></a>手順 3 - Office をアンインストールする

Office の最新バージョンをインストールする前に、以前のバージョンの Office をすべてアンインストールすることをお勧めします。 ただし、Office のアップグレードに関する注意事項を変更した場合は、次のような状況で、アンインストール後に Office を再インストールできないことに注意してください。
  
サードパーティのアドインを使用している場合は、最新バージョンの Office で動作する更新プログラムがあるかどうかを製造元に問い合わせて確認することをお勧めします。

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>アンインストールするバージョンの Office を選択します

- [PC から](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac から](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>以前のバージョンの Office をアンインストール後に再インストールできない既知の問題

 **ボリュームライセンスを使用した Office** これらのボリュームライセンスバージョンの Office のソースファイルにアクセスできなくなった場合は、再インストールすることはできません。

 **コンピューターにプレインストールされている Office** ディスクまたはプロダクトキーがない場合 (Office がある場合)、再インストールすることはできません。

 **サポートされていないサブスクリプション** Office のコピーが、Office 365 Small Business Premium または Office 365 の中規模企業など、廃止されたサブスクリプションを通じて取得した場合、サブスクリプションに付属のプロダクトキーを使用していない限り、以前のバージョンの Office をインストールすることはできません。

以前のバージョンの Office と最新版を共存させる場合、「[異なるバージョンの Office を同じ PC にインストールして使う](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)」で、共存が可能なバージョンの一覧をご確認いただけます。たとえば、サードパーティ アドインをインストールして以前のバージョンの Office で使用しているとき、アドインと最新版の Office の間に互換性があるかどうかがわからない場合は、共存インストールが正しい選択となることがあります。

## <a name="step-4---assign-office-licenses-to-users"></a>手順 4 - Office ライセンスをユーザーに割り当てる

まだインストールしていない場合は、Office をインストールする必要がある組織内のユーザーにライセンスを割り当てます。詳細については、「 [Microsoft 365 for business でユーザーにライセンスを割り当てる](../manage/assign-licenses-to-users.md)」を参照してください。
  
## <a name="step-5---install-office"></a>手順 5 - Office をインストールする

アップグレードするユーザーにライセンスがあることを確認したら、最後に Office をインストールするには、「 [PC または Mac に office をダウンロードしてインストールまたは再](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)インストールする」を参照してください。
  
> [!TIP]
> ユーザーに Office をインストールさせたくない場合は、「 [Manage software download settings In office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)」を参照してください。 Office [展開ツール](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) を使用して office ソフトウェアをローカルネットワークにダウンロードし、通常使用するソフトウェア展開方法を使用して office を展開することができます。
