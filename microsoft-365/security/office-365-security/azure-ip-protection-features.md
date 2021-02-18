---
title: Azure Information Protection の保護機能が既存のテナントに展開される
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、Azure Information Protection の保護機能に展開される変更について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe85a46e3f20cda62cd8a52bd5df92257f8fee57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286671"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Azure Information Protection の保護機能が既存のテナントに展開される

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

情報を保護するための最初の手順を支援するために、2018 年 7 月からすべての Azure Information Protection の対象テナントで、Azure Information Protection の保護機能が既定で有効になります。 Azure Information Protection の保護機能は、以前は Office 365 で Rights Management または Azure RMS として知られています。 組織に Office E3 サービス プラン以上のサービス プランがある場合、これらの機能のロールアウト時に Azure Information Protection を通じて情報の保護を開始できます。

## <a name="changes-beginning-july-1-2018"></a>2018 年 7 月 1 日から変更

2018 年 7 月 1 日から、Microsoft は次のいずれかのサブスクリプション プランを持つすべての組織に対して Azure Information Protection の保護機能を有効にします。

- Office 365 Message Encryption は、Office 365 E3 および E5、Microsoft E3 と E5、Office 365 A1、A3、A5、および Office 365 G3 および G5 の一部として提供されます。 Azure Information Protection が提供する新しい保護機能を受け取る場合は、追加のライセンスは必要ではありません。

- Azure Information Protection プラン 1 を次のプランに追加して、新しい Office 365 Message Encryption 機能を受信できます。Exchange Online プラン 1、Exchange Online プラン 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 Business Standard、または Office 365 Enterprise E1。

- 365 Message Encryption Officeを利用する各ユーザーには、この機能の対象となるライセンスが必要です。

- 完全な一覧については [、365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Message Encryption の Exchange Online サービスOffice参照してください。

テナント管理者は、Office 365 管理者ポータルで保護の状態を確認できます。

![Office 365 の権限管理がアクティブ化された状態を示すスクリーンショット。](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>この変更を行う理由

Office 365 Message Encryption は、Azure Information Protection の保護機能を活用します。 Office 365 Message Encryption の最近の改善の中心であり、Microsoft 365 の情報保護に対する広範な投資により、従来、暗号化テクノロジのセットアップは困難であったので、組織が保護機能を有効にし、使用しやすくなっています。 Azure Information Protection の保護機能を既定で有効にすることで、機密データの保護をすばやく開始できます。

## <a name="does-this-impact-me"></a>これは私に影響しますか?

組織が 365 ライセンスのOffice購入している場合、テナントはこの変更の影響を受け取る可能性があります。

> [!IMPORTANT]
> オンプレミス環境で Active Directory Rights Management サービス (AD RMS) を使用している場合は、今後 30 日以内にこの変更をロールアウトする前に、この変更を直ちにオプトアウトするか、Azure Information Protection に移行する必要があります。 オプトアウトの方法については、「RMS を使用するADオプトアウトする方法」を参照してください。 」で説明する手順に従ってローカライズされたファイルをインストールします。 移行する場合は、「RMS から[Azure Information Protection への移行AD」を参照してください。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Azure Information Protection を Active Directory Rights Management サービス (AD RMS) と一緒に使用できますか。

いいえ。 これは、サポートされている展開シナリオではありません。 追加のオプトアウト手順を実行せずに、一部のコンピューターは Azure Rights Management サービスの使用を自動的に開始し、AD RMS クラスターに接続する場合があります。 このシナリオはサポートされていないので、結果が不当です。そのため、これらの新機能を展開する前に、今後 30 日以内にこの変更をオプトアウトすることが重要です。 オプトアウトの方法については、「RMS を使用するADオプトアウトする方法」を参照してください。 」で説明する手順に従ってローカライズされたファイルをインストールします。 移行する場合は、「AD RMS から Azure Information Protection への移行」を [参照してください。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>RMS を使用している場合のAD方法

[ACTIVE DIRECTORY RIGHTS MANAGEMENT サービス (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)も展開している場合は、「Azure Rights Management の環境を準備する」の手順にADしてください。

1. オプションですが、RMS ADのほとんどの展開では、サービス接続ポイント (SCP) を Active Directory に公開して、ドメイン コンピューターが新しい RMS クラスターをADできます。

   ADSI Edit を使用して、Active Directory に SCP が公開されているかどうかを確認します。CN=Configuration [サーバー名]、CN=Services、CN=RightsManagementServices、CN=SCP

2. SCP を使用していない場合、AD RMS クラスターに接続する Windows コンピューターは、Windows レジストリを使用してクライアント側のサービス検出またはライセンス リダイレクト用に構成する必要があります `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` 。

これらのレジストリ構成の詳細については [、「Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) レジストリを使用したクライアント側サービス検出の有効化」および「ライセンス サーバー トラフィックのリダイレクト」を [参照してください](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>RMS をAD、オプトアウトする方法

今後の変更からオプトアウトするには、次の手順を実行します。

1. 組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. 次の構文Set-IRMConfigurationコマンドレットを実行します。

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>この変更が行われた後、どのようなことを期待できますか。

これを有効にした後、オプトアウトしていない場合は [、Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) で発表され、Azure Information Protection の暗号化と保護機能を活用する新しいバージョンの Office 365 Message Encryption の使用を開始できます。

![Outlook on the web で OME で保護されたメッセージを示すスクリーンショット。](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

新しい拡張機能の詳細については、「Office [365 Message Encryption」を参照してください](../../compliance/ome.md)。
