---
title: Windows 10 Enterprise を組織で展開するための準備
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869533"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>手順 1: Windows 10 Enterprise を組織で展開するための準備

*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

デバイスを Windows 10 Enterprise にアップグレードする前に、以下のことを検討してください:

- **ドメインの追加と確認が必要** <br>Microsoft 365 のサブスクリプションでは、末尾が onmicrosoft.com の既定のドメイン名が発行されます (例: contoso.onmicrosoft.com)。多くの組織は、所有するドメインを 1 つまたは複数使用して、メール アドレスの末尾に独自のドメイン名を使うことを希望します (username@contoso.com など)。独自のドメインを使うには Microsoft 365 へのドメインの追加と、所有確認が必要です。メールや Skype for Business などの Microsoft 365 サービスの設定を行うときに独自ドメインが利用できる状態にしておくために、すぐにドメインを追加して確認することをお勧めします。
- **この時点でユーザーを追加する必要はありません** <br>Microsoft 365 サービスの使用または Microsoft 365 製品をインストールするには、ユーザーが Microsoft 365 のアカウントと製品ライセンスを持っている必要があります。Microsoft 365 にユーザーを追加する方法は、ユーザーの数とオンプレミスの Active Directory を現在所有しているかどうかにより異なります。Active Directory を持っていない (または Active Directory を持っているが Microsoft 365 と同期させたくない) 場合は、ユーザーを Microsoft 365 に直接追加し、個別または一括でライセンスの割り当てを行うことができます。<br>オンプレミスの Active Directory を持っている場合は、それを [Microsoft 365 と同期](identity-azure-ad-connect-health.md)して、Microsoft 365 が利用するクラウド ディレクトリの Azure AD にユーザー アカウントを作成できます。この方法を使い、(SharePoint Online サイト コ レクションやドキュメントなどの) リソースへのアクセス許可の管理に使用するユーザーのアカウントとセキュリティ グループを作成できます。Active Directory を Microsoft 365 と同期してもユーザーにライセンスは割り当てられません。
- **この時点でユーザーにライセンスを割り当てる必要はありません** <br>Microsoft 365 サービスの使用または Microsoft 365 ポータルからソフトウェアをインストールするには、ユーザーは製品のライセンスを持っている必要があります。グローバル管理またはユーザー管理の管理者は、Microsoft 365 の製品ライセンスを個別または一括で直接割り当てることができます。また、[グループベースのライセンス割り当て](identity-group-based-licensing.md)を使い、ユーザーが特定のグループに追加されたときにライセンスが自動的に割り当てられるように設定できます。 
- **Office 365 ProPlus は別にインストール** <br>Microsoft 365 のライセンスを入手しても、Office 365 ProPlus はクライアント コンピューターに自動的にインストールされません。詳細は「[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md)」参照してください。 

## <a name="set-windows-diagnostics-data-level"></a>Windows 診断プログラムのデータのレベルを設定します。

Microsoft は診断データを使用してマルウェアの傾向やその他の脅威を特定し、Windows および Microsoft のサービスを向上させて、Windows デバイスを保護します。診断サービスが、組織内のすべてのエンドポイントで少なくとも基本レベルで有効になっていることを確認する必要があります。*既定では、このサービスが強化レベルに設定されています。* ただし、センサー データを確実に受信していることを確認してください。ポリシーを使用してレベルを設定すると、デバイス レベルの設定が上書きされます。 

**Windows 10 オペレーティング システムの診断データ レベル**

使用して、グループ ポリシー、MDM では、Windows の準備などの管理ツールを使用してオペレーティング システム診断データ設定を構成することができます。手動で、レジストリ エディターを使用して設定を変更することができます。管理ポリシーを使用して診断データのレベルを設定すると、任意のデバイス レベルの設定が上書きされます。

管理ポリシーを構成するときに、次の表の適切な値を参照してください。

| レベル | 収集されるデータ | 値 |
|:--- |:--- |:--- |
| セキュリティ | セキュリティ データのみ。 | 0 |
| 基本 | セキュリティ データ、および基本的なシステムと品質のデータ。 | 1 |
| 強化 | セキュリティ データ、基本的なシステムと品質のデータ、強化された分析および高度な信頼性データ。 | 2 |
| 完全 | セキュリティ データ、基本的なシステムと品質のデータ、強化された分析および高度な信頼性データ、および完全な診断データ。 | 3 |

次のいずれかの方法で診断データを有効にすることができます。

* 
  **Microsoft Intune**: Intune を使用してデバイスを管理する場合、<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> システム ポリシーを構成し、診断データを有効化する構成ポリシーを作成することができます。構成のポリシーの設定の詳細については、「[Microsoft Intune ポリシーを使用してデバイスの設定や機能を管理する](https://aka.ms/intuneconfigpolicies)」 を参照してください。
* **レジストリ エディター**: レジストリ エディターを使用し、組織内の各デバイスの診断データを手動で有効にすることができます。また、レジストリを編集するスクリプトを作成することもできます。グループ ポリシーや MDM など、管理ポリシーがすでに存在する場合は、このレジストリ設定よりも優先されます。
* **グループ ポリシー** - Intune でデバイスを登録するのに予定がない場合、組織の診断データのレベルを設定するのには、グループ ポリシー オブジェクトを使用できます。
* **コマンド プロンプト**: コマンド プロンプトを使用し、Windows 10 の診断データとサービスが自動的に開始するように設定できます。この方法は少数のデバイスのみで、サービスをテストしている場合に最適です。このコマンドを使用してサービスを自動的に開始する場合、診断データ レベルは構成されません。管理ツールを使用して診断データ レベルを構成していない場合は、サービスは既定の強化レベルで動作します。

Windows 診断データの詳細と選択した方法に基づき有効化する方法については、「[組織内で Windows 診断データを構成する](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)」 を参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step1)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [インプレース アップグレードによる Windows 10 Enterprise の既存デバイスへの展開](windows10-deploy-inplaceupgrade.md) |






