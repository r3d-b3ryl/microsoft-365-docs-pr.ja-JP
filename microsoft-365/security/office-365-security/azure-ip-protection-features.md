---
title: Azure の保護機能Information Protection既存のテナントにロールアウトする
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、Azure Information Protectionの保護機能に対する変更について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38dd1accf4641d6dfe3f66574b1072e2500cb914
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65647823"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Azure の保護機能Information Protection既存のテナントにロールアウトする

**適用対象**
- [Microsoft Defender for Office 365 プラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

情報の保護の最初の手順を支援するために、2018 年 7 月以降、すべての Azure Information Protection対象テナントに対して、既定で Azure Information Protectionの保護機能が有効になります。 Azure Information Protection の保護機能は、以前は Rights Management または Azure RMS としてOffice 365で知られていました。 組織にOffice E3 サービス プラン以上のサービス プランがある場合は、これらの機能をロールアウトするときに、Azure Information Protectionを通じて情報の保護を開始できるようになります。

## <a name="changes-beginning-july-1-2018"></a>2018 年 7 月 1 日以降の変更

2018 年 7 月 1 日から、Microsoft は、次のいずれかのサブスクリプション プランを使用して、すべての組織に対して Azure Information Protectionの保護機能を有効にします。

- Office 365メッセージ暗号化は、Office 365 E3と E5、Microsoft E3、E5、Office 365 A1、A3、A5、および Office 365 G3 および G5 の一部として提供されます。 Azure Information Protectionを搭載した新しい保護機能を受け取るために追加のライセンスは必要ありません。

- Office 365 Message Encryption の新機能を利用するために、次のプランに Azure Information Protection プラン 1 を追加することもできます: Exchange Online プラン 1、Exchange Online プラン 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 Business Standard、Office 365 Enterprise E1。

- Office 365 Message Encryption を利用するすべてのユーザーは、この機能の対象になるためにはライセンスが付与される必要があります。

- 完全な一覧については、Office 365 メッセージ暗号化の[Exchange Online サービスの説明](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)を参照してください。

テナント管理者は、Office 365管理者ポータルで保護の状態を確認できます。

:::image type="content" source="../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png" alt-text="アクティブ化されるOffice 365の権限管理" lightbox="../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png":::

## <a name="why-are-we-making-this-change"></a>この変更を行う理由

Office 365 メッセージ暗号化では、Azure Information Protectionの保護機能が活用されます。 メッセージ暗号化のOffice 365に対する最近の機能強化と、Microsoft 365での情報保護への広範な投資の中心として、従来は暗号化テクノロジの設定が困難であったように、組織が保護機能を有効にして使用しやすくしています。 Azure Information Protectionの保護機能を既定で有効にすると、機密データの保護をすばやく開始できます。

## <a name="does-this-impact-me"></a>これは影響を受けますか?

組織が適格なOffice 365ライセンスを購入した場合、テナントはこの変更の影響を受けます。

> [!IMPORTANT]
> オンプレミス環境で Active Directory Rights Management サービス (AD RMS) を使用している場合は、この変更を直ちにオプトアウトするか、Azure Information Protectionに移行してから、今後 30 日以内にこの変更を展開する必要があります。 オプトアウトする方法については、「AD RMS を使用する方法、オプトアウトする方法」を参照してください。 」で説明する手順に従ってローカライズされたファイルをインストールします。 移行する場合は、「[AD RMS から Azure Information Protectionへの移行](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Active Directory Rights Management サービス (AD RMS) で Azure Information Protectionを使用できますか?

いいえ。 これは、サポートされているデプロイ シナリオではありません。 追加のオプトアウト手順を実行しないと、一部のコンピューターで Azure Rights Management サービスの使用が自動的に開始され、AD RMS クラスターにも接続されることがあります。 このシナリオはサポートされておらず、信頼性の低い結果が得られないため、これらの新機能をロールアウトする前に、今後 30 日以内にこの変更をオプトアウトすることが重要です。 オプトアウトする方法については、「AD RMS を使用する方法、オプトアウトする方法」を参照してください。 」で説明する手順に従ってローカライズされたファイルをインストールします。 移行する場合は、「[AD RMS から Azure Information Protectionへの移行](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。

## <a name="how-do-i-know-if-im-using-ad-rms"></a>AD RMS を使用しているかどうかを確認操作方法。

AD RMS をデプロイしたかどうかを確認[するには、Active Directory Rights Management サービス (AD RMS) がある場合に Azure Rights Management用の環境を準備](/azure/information-protection/deploy-use/prepare-environment-adrms)するに関するページの手順を参照してください。

1. オプションですが、ほとんどの AD RMS 展開では、ドメイン コンピューターが AD RMS クラスターを検出できるように、Active Directory にサービス接続ポイント (SCP) を発行します。

   ADSI Edit を使用して、ACTIVE Directory で SCP が発行されているかどうかを確認します。CN=Configuration [サーバー名]、CN=Services、CN=RightsManagementServices、CN=SCP

2. SCP を使用していない場合は、WINDOWS レジストリ`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`を使用して、AD RMS クラスターに接続するWindows コンピューターをクライアント側のサービス検出またはライセンス リダイレクト用に構成する必要があります。

これらのレジストリ構成の詳細については、「[Windows レジストリを使用したクライアント側サービス検出の有効化](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)と[ライセンス サーバー トラフィックのリダイレクト」を参照してください](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>AD RMS を使用する場合、オプトアウトする方法を教えてください。

今後の変更をオプトアウトするには、次の手順を実行します。

1. 組織内のグローバル管理者アクセス許可を持つ職場または学校アカウントを使用して、Windows PowerShell セッションを開始し、Exchange Onlineに接続します。 手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. 次の構文を使用して、Set-IRMConfiguration コマンドレットを実行します。

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>この変更が行われた後は何が期待できますか?

これが有効になったら、オプトアウトしていない場合は、[Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) で発表された新しいバージョンの Office 365 メッセージ暗号化の使用を開始し、Azure Information Protectionの暗号化と保護機能を活用できます。

:::image type="content" source="../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png" alt-text="Outlook on the webの OME で保護されたメッセージ" lightbox="../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png":::

新しい機能強化の詳細については、「[メッセージ暗号化のOffice 365」を](../../compliance/ome.md)参照してください。
