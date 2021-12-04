---
title: 手順 5.  Microsoft Intune にデバイス プロファイルを展開する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: 4f0847c70f5293a50cdaf80e657be5b5ac8753b4
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301344"
---
# <a name="step-5-deploy-device-profiles-in-microsoft-intune"></a>手順 5.  Microsoft Intune にデバイス プロファイルを展開する

Microsoft Intune には、組織内のさまざまなデバイスで有効または無効にできる設定と機能が含まれています。 これらの設定と機能は "構成プロファイル" に追加されます。 iOS/iPad OS、Android デバイス管理者、Android Enterprise、Windows など、さまざまなデバイスやプラットフォームのプロファイルを作成できます。 次に、Intune を使用して、プロファイルをデバイスに適用または「割り当て」ます。

この記事では、構成プロファイルの使用を開始するためのガイダンスを提供します。 


![デバイスを管理するための手順](../media/devices/intune-mdm-step-4.png#lightbox)

構成プロファイルを使用すると、重要な保護を構成し、デバイスをコンプライアンスに準拠させて、リソースにアクセスできるようにすることができます。 以前は、これらの種類の構成変更は、Active Directory ドメイン サービスのグループ ポリシー設定を使用して構成されていました。 最新のセキュリティ戦略には、セキュリティ制御をクラウドに移行することが含まれますが、これらの実施はオンプレミスのリソースとアクセスに依存しません。 Intune 構成プロファイルは、これらのセキュリティ コントロールをクラウドに移行する方法です。 

作成できる構成プロファイルの種類については、「[Microsoft Intune のデバイス プロファイルを使用してデバイスに機能と設定を適用する](/mem/intune/configuration/device-profiles)」を参照してください。

## <a name="deploy-windows-security-baselines-for-intune"></a>Intune の Windows セキュリティ ベースラインを展開する

開始点として、デバイス構成を Microsoft セキュリティ ベースラインに合わせる場合は、Microsoft Endpoint Manager 内のセキュリティ ベースラインをお勧めします。 このアプローチの利点は、Windows 10 および 11 の機能がリリースされたときに、Microsoft がベースラインを最新の状態に保つことを信頼できることです。 

Intune の Windows セキュリティ ベースラインを展開するには、Windows 10 および Windows 11 で使用できます。 使用可能なベースラインについては、「[セキュリティ ベースラインを使用して Intune で Windows デバイスを構成する](/mem/intune/protect/security-baselines)」を参照してください。

今のところ、最も適切な MDM セキュリティ ベースラインを展開します。 プロファイルを作成してベースライン バージョンを選択するには、「[Microsoft Intune でのセキュリティ ベースライン プロファイルの管理](/mem/intune/protect/security-baselines-configure)」を参照してください。

後で、Microsoft Defender for Endpoint がセットアップされ、Intune に接続したら、Defender for Endpoint ベースラインを展開します。 これについては、このシリーズの次の記事で説明します。[手順 6. デバイスのリスクとセキュリティ ベースラインへのコンプライアンスを監視する](manage-devices-with-intune-monitor-risk.md)。

これらのセキュリティ ベースラインは CIS または NIST に準拠していませんが、推奨事項を厳密に反映していることを理解することが重要です。 詳細については、「[Intune セキュリティ ベースラインは CIS または NIST に準拠していますか](/mem/intune/protect/security-baselines)?」を参照してください。

## <a name="customize-configuration-profiles-for-your-organization"></a>組織の構成プロファイルをカスタマイズする

事前構成されたベースラインの展開に加えて、多くの企業規模の組織は、よりきめ細かい制御のために構成プロファイルを実装しています。 事前構成されたベースラインの展開に加えて、多くの企業規模の組織は、よりきめ細かい制御のために構成プロファイルを実装しています。 

構成プロファイルを使用して構成できる多くの設定は、以下に示すように 4 つのカテゴリーにグループ化できます。

![Intune デバイス プロファイルのカテゴリ](../media/devices/intune-device-profile-categories.png#lightbox)

次の表で、図について説明します。


|カテゴリ |説明 |例  |
|---------|---------|---------|
|デバイスの機能     | デバイスの機能を制御します。 このカテゴリは、iOS / iPadOS および macOS デバイスにのみ適用されます。        | Airprint、通知、ロック画面メッセージ        |
|デバイスの制限     | デバイスのセキュリティ、ハードウェア、データ共有、その他の設定を制御する        | PIN、データ暗号化を要求する        |
|アクセス構成     |  組織のリソースにアクセスするデバイスを構成する        | メール プロファイル、VPN プロファイル、Wi-Fi設定、証明書        |
|Custom     | カスタム構成の設定またはカスタム構成アクションの実行       | OEM 設定の設定、PowerShell スクリプトの実行        |
|    |         |         |

組織の構成プロファイルをカスタマイズする場合は、次のガイダンスを使用します。
- ポリシーの総数を少なくして、セキュリティ ガバナンス戦略を簡素化します。
- 設定を上記のカテゴリ、または組織に合ったカテゴリにグループ化します。
- セキュリティコントロールをグループ ポリシー オブジェクト (GPO) から Intune 構成プロファイルに移動する場合は、各 GPO で構成された設定が引き続き関連性が高く、全体的なクラウド セキュリティ戦略に貢献するために必要かどうかを検討します。 条件付きアクセスと、Intune を含むクラウド サービス全体で構成できる多数のポリシーは、カスタム GPO が最初に設計されたオンプレミス環境で構成できるよりも高度な保護を提供します。
- グループポリシー分析を利用して、現在の GPO 設定を Microsoft Endpoint Manager 内の機能と比較およびマッピングします。 Microsoft Endpoint Manager の「[グループ ポリシー分析を使用してオンプレミスのグループ ポリシー オブジェクト (GPO) を分析する](/mem/intune/configuration/group-policy-analytics)」を参照してください。
- カスタム構成プロファイルを利用する場合は、必ず次のガイダンスを使用してください: 「[Intune でカスタム設定を使用してプロファイルを作成する](/mem/intune/configuration/custom-settings-configure)」。

## <a name="additional-resources"></a>その他のリソース

デバイス プロファイルの開始場所がわからない場合は、次のことが役立ちます。

- [ガイド付きのシナリオ](/mem/intune/fundamentals/guided-scenarios-overview) 
- [セキュリティ基本計画](/mem/intune/protect/security-baselines)

環境にオンプレミス GPO が含まれている場合、次の機能はクラウドへの適切な移行です。

- [グループ ポリシー分析](/mem/intune/configuration/group-policy-analytics)
- [管理テンプレート (ADMX)](/mem/intune/configuration/administrative-templates-windows)
- [設定カタログ](/mem/intune/configuration/settings-catalog)


## <a name="next-steps"></a>次の手順
「[手順 6. デバイスのリスクとセキュリティ ベースラインへの準拠を監視する](manage-devices-with-intune-monitor-risk.md)」に進みます。