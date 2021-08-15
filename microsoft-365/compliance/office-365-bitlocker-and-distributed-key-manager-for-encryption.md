---
title: 暗号化用 BitLocker
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: BitLocker 暗号化Office 365、コンピューターやディスクの紛失または盗難によるデータ盗難の可能性を減らす方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 71aeef37b2b9683acdb6fad0b26a0d567aea4f269e5f820f73cf772b9c88efd9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53855901"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker と Distributed Key Manager (DKM) による暗号化

Microsoft サーバーは、BitLocker を使用して、ボリューム レベルで保存されている顧客データを含むディスク ドライブを暗号化します。 BitLocker 暗号化は、Windows に組み込まれているデータ保護機能です。 BitLocker は、顧客データが含まれるディスクに何者かが物理的にアクセスできるようになりかねない過失がプロセスや制御 (アクセス制御またはハードウェアのリサイクルなど) で生じた場合に、脅威から安全に保護するために使用されるテクノロジの 1 つです。 その場合、BitLocker は、コンピューターやディスクの紛失、盗難、または不適切な廃棄によるデータの盗難や漏洩などの脅威の可能性を低減します。

BitLocker は、Exchange Online、SharePoint Online、および Skype for Business の顧客データを含むディスクに高度な暗号化標準 (AES) 256 ビット暗号化を使用して展開されます。 ディスク セクターは、ボリューム マスター キー (VMK) で暗号化されるフル ボリューム暗号化キー (FVEK) で暗号化され、サーバー内のトラステッド プラットフォーム モジュール (TPM) にバインドされます。 VMK は FVEK を直接保護するため、VMK の保護が重要になります。 次の図は、特定のサーバーの BitLocker キー保護チェーンの例を示しています (この場合は、サーバーを使用Exchange Onlineします。

次の表に、特定のサーバーの BitLocker キー保護チェーン (この場合は、サーバー Exchange Onlineします。

| キー プロテクター | 粒度 | どのように生成されますか? | どこに保存されますか? | PROTECTION |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256 ビット外部キー | サーバーごとに | BitLocker API | TPM またはシークレット セーフ | Lockbox / Access Control |
|  |  |  | メールボックス サーバーレジストリ | TPM の暗号化 |
| 48 桁の数値パスワード | ディスクごとに | BitLocker API | Active Directory | Lockbox / Access Control |
| X.509 データ復旧エージェントとしての証明書 (DRA) は、パブリック キー プロテクターとも呼ばれる | 環境 (マルチテナントExchange Onlineなど) | Microsoft CA | ビルド システム | プライベート キーに対する完全なパスワードを持つユーザーは 1 人もいはありません。 パスワードは物理的な保護の下にある。 |


BitLocker キー管理には、Microsoft データセンター内の暗号化されたディスクのロック解除および回復に使用される回復キーの管理が含まれます。 Microsoft 365 は、審査を受けて承認された個人のみがアクセスできるセキュリティで保護された共有にマスター キーを保存します。 キーの資格情報は、アクセス制御データ ("シークレット ストア" と呼ばれる) 用のセキュリティで保護されたリポジトリに格納され、Just-in-time アクセス昇格ツールを使用してアクセスするには、高レベルの昇格と管理の承認が必要です。

BitLocker は、次の 2 つの管理カテゴリに分類されるキーをサポートしています。

- BitLocker で管理されるキーは、一般的に有効期間が短く、サーバーにインストールされているオペレーティング システムのインスタンス、または指定されたディスクの有効期間に関連付けられています。 これらのキーは、サーバーの再インストールまたはディスクのフォーマット中に削除され、リセットされます。

- BitLocker の回復キーは、BitLocker の外部で管理されますが、ディスクの暗号化解除に使用されます。 BitLocker は、オペレーティング システムが再インストールされ、暗号化されたデータ ディスクがすでに存在する場合のシナリオで、回復キーを使用します。 回復キーは、応答者がディスクのロックを解除する必要がある Exchange Online の管理された可用性監視プローブでも使用されます。

BitLocker で保護されたボリュームは、ボリューム マスター キーで暗号化されるフル ボリューム暗号化キーで暗号化されます。 BitLocker は、FIPS 準拠のアルゴリズムを使用して、暗号化キーがクリアでワイヤーを使用して保存または送信されるのを確実にします。 Microsoft 365 による保管中の顧客データ保護の実装は、既定の BitLocker の実装から逸脱するのものではありません。
