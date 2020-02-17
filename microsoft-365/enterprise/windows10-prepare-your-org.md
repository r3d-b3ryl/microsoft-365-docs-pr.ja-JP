---
title: Windows 10 Enterprise を組織で展開するための準備
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 Enterprise、Microsoft 365 ドキュメント、Windows 10 Enterprise、展開
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 9b83082a4dc859c10db03608de2edebdbb633cbe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085526"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>手順 1: Windows 10 Enterprise を組織で展開するための準備

*この記事は、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*

![フェーズ 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

デバイスを Windows 10 Enterprise にアップグレードする前に、以下のことを検討してください:

- **ドメインの追加と確認が必要** <br>Microsoft 365 のサブスクリプションでは、末尾が onmicrosoft.com の既定のドメイン名が発行されます (例: contoso.onmicrosoft.com)。多くの組織は、所有するドメインを 1 つまたは複数使用して、メール アドレスの末尾に独自のドメイン名を使うことを希望します (username@contoso.com など)。独自のドメインを使うには Microsoft 365 へのドメインの追加と、所有確認が必要です。メールや Skype for Business などの Microsoft 365 サービスの設定を行うときに独自ドメインが利用できる状態にしておくために、すぐにドメインを追加して確認することをお勧めします。
- **この時点でユーザーを追加する必要はありません** <br>Microsoft 365 サービスの使用または Microsoft 365 製品をインストールするには、ユーザーが Microsoft 365 のアカウントと製品ライセンスを持っている必要があります。Microsoft 365 にユーザーを追加する方法は、ユーザーの数とオンプレミスの Active Directory を現在所有しているかどうかにより異なります。Active Directory を持っていない (または Active Directory を持っているが Microsoft 365 と同期させたくない) 場合は、ユーザーを Microsoft 365 に直接追加し、個別または一括でライセンスの割り当てを行うことができます。<br>オンプレミスの Active Directory を持っている場合は、それを [Microsoft 365 と同期](identity-add-user-accounts.md#identity-sync)して、Microsoft 365 が利用するクラウド ディレクトリの Azure AD にユーザー アカウントを作成できます。この方法を使い、(SharePoint Online サイト コ レクションやドキュメントなどの) リソースへのアクセス許可の管理に使用するユーザーのアカウントとセキュリティ グループを作成できます。Active Directory を Microsoft 365 と同期してもユーザーにライセンスは割り当てられません。
- **この時点でユーザーにライセンスを割り当てる必要はありません** <br>Microsoft 365 サービスの使用または Microsoft 365 ポータルからソフトウェアをインストールするには、ユーザーは製品のライセンスを持っている必要があります。グローバル管理またはユーザー管理の管理者は、Microsoft 365 の製品ライセンスを個別または一括で直接割り当てることができます。また、[グループベースのライセンス割り当て](identity-use-group-management.md#identity-group-license)を使い、ユーザーが特定のグループに追加されたときにライセンスが自動的に割り当てられるように設定できます。 
- **Office 365 ProPlus は別にインストール** <br>Microsoft 365 のライセンスを入手しても、Office 365 ProPlus はクライアント コンピューターに自動的にインストールされません。詳細は「[フェーズ 4: Office 365 ProPlus](office365proplus-infrastructure.md)」参照してください。 

## <a name="set-windows-diagnostics-data-level"></a>Windows 診断データレベルを設定する

Microsoft では、診断データを使用して、マルウェアの傾向やその他の脅威を特定し、windows や Microsoft サービスの品質を向上するために、Windows デバイスのセキュリティを確保しています。 組織内のすべてのエンドポイントで、診断サービスが最小限の基本レベルで有効になっていることを確認する必要があります。 *既定では、このサービスは有効になっており、Enhanced レベルに設定されています。* ただし、センサーデータを受信していることを確認して確認することをお勧めします。 ポリシーによるレベルの設定は、デバイスレベルの設定より優先されます。 

**Windows 10 オペレーティングシステム診断データレベル**

グループポリシー、MDM、Windows の準備など、既に使用している管理ツールを使用して、オペレーティングシステム診断データの設定を構成できます。 レジストリエディターを使用して、手動で設定を変更することもできます。 管理ポリシーを使用して診断データレベルを設定すると、デバイスレベルの設定はすべて無視されます。

管理ポリシーを構成するときは、次の表に示す適切な値を使用します。

| レベル | 収集されたデータ | 値 |
|:--- |:--- |:--- |
| セキュリティ | セキュリティデータのみ。 | .0 |
| 基本 | セキュリティデータ、および基本的なシステムと品質のデータ。 | 1-d |
| 保護 | セキュリティデータ、基本的なシステムと品質のデータ、強化された洞察および高度な信頼性データ。 | pbm-2 |
| Full | セキュリティデータ、基本的なシステムと品質のデータ、強化された洞察および高度な信頼性データ、および完全な診断データ。 | 1/3 |

診断データを有効にするには、次のいずれかの方法を使用します。

* **Microsoft Intune** : Intune を使用してデバイスを管理する予定の場合は、 <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">systemallowtelemetry</a>システムポリシーを構成して診断データを有効にする構成ポリシーを作成できます。 構成ポリシーの設定の詳細については、「 [Microsoft Intune ポリシーを使用してデバイスの設定と機能を管理](https://aka.ms/intuneconfigpolicies)する」を参照してください。
* **レジストリエディター** -レジストリエディターを使用して、組織内の各デバイスで診断データを手動で有効にすることができます。 または、レジストリを編集するスクリプトを記述することもできます。 グループポリシーまたは MDM などの管理ポリシーが既に存在する場合は、このレジストリ設定が上書きされます。
* **グループポリシー** -Intune にデバイスを登録する予定がない場合は、グループポリシーオブジェクトを使用して、組織の診断データレベルを設定できます。
* **コマンドプロンプト**-Windows 10 診断データおよびサービスを、コマンドプロンプトで自動的に開始するように設定できます。 この方法は、サービスを少数のデバイスでのみテストする場合に最適です。 このコマンドを使用してサービスを自動的に開始できるようにする場合は、診断データレベルを構成しません。 管理ツールを使用して診断データレベルを構成していない場合、サービスは既定の拡張レベルで動作します。

Windows 診断データの詳細と、選択した方法に基づいて有効にする方法については、「[組織で windows 診断データを構成](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)する」を参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](windows10-exit-criteria.md#crit-windows10-step1)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 2](../media/stepnumbers/Step2.png)| [インプレース アップグレードによる Windows 10 Enterprise の既存デバイスへの展開](windows10-deploy-inplaceupgrade.md) |






