---
title: 証明書に基づいてインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義する証明書に基づいてインジケーターを作成します。
keywords: ioc、証明書、証明書、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164683"
---
# <a name="create-indicators-based-on-certificates"></a>証明書に基づいてインジケーターを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

証明書のインジケーターを作成できます。 一般的な使用例には、次のようなものがあります。

- 攻撃表面の縮小ルールやフォルダー アクセスの制御[](attack-surface-reduction.md)など、ブロック テクノロジ[](controlled-folders.md)を展開する必要があるが、許可リストに証明書を追加して署名済みアプリケーションからの動作を許可する必要があるシナリオ。
- 組織全体で特定の署名付きアプリケーションの使用をブロックする。 アプリケーションの証明書をブロックするインジケーターを作成すると、Windows Defender AV はファイルの実行 (ブロックと修復) を防止し、自動調査と修復は同じように動作します。


### <a name="before-you-begin"></a>はじめに

証明書のインジケーターを作成する前に、次の要件を理解することが重要です。

- この機能は、組織でウイルス対策とクラウドベースWindows Defenderが有効になっている場合に使用できます。 詳細については、「クラウドベースの保護 [を管理する」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)。
- マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。
- Windows 10 バージョン 1703 以降の Windows Server 2016 および 2019 のコンピューターでサポートされます。
- ウイルスおよび脅威保護の定義は最新である必要があります。
- この機能は現在、 の入力をサポートしています。CER または .PEM ファイル拡張子。

>[!IMPORTANT]
> - 有効なリーフ証明書は、有効な証明書パスを持ち、Microsoft が信頼するルート証明機関 (CA) にチェーンする必要がある署名証明書です。  または、カスタム (自己署名証明書) 証明書は、クライアントによって信頼されている限り使用できます (ルート CA 証明書は、ローカル コンピューターの [信頼されたルート証明機関] の下にインストールされます)。
>- 許可/ブロック証明書 IOC の子または親は、許可/ブロック IoC 機能には含まれません。リーフ証明書だけがサポートされます。
>- Microsoft 署名された証明書はブロックできません。

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>設定ページから証明書のインジケーターを作成します。

>[!IMPORTANT]
> 証明書 IoC を作成および削除するには、最大 3 時間かかる場合があります。

1. ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。  

2. [証明書] **タブを選択** します。

3. [インジケーター **の追加] を選択します**。

4. 次の詳細を指定します。
   - Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。
   - Action - 実行するアクションを指定し、説明を入力します。
   - Scope - コンピューター グループのスコープを定義します。

5. [概要] タブで詳細を確認し、[保存] を **クリックします**。

## <a name="related-topics"></a>関連項目
- [インジケーターの作成](manage-indicators.md)
- [ファイルのインジケーターを作成する](indicator-file.md)
- [IPs と URL/ドメインのインジケーターを作成する](indicator-ip-domain.md)
- [インジケーターの管理](indicator-manage.md)
