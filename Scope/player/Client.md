# Client

The client for the player that the server is handling.

### Code

```javascript
export class Client extends EventEmitter {
	constructor(isServer: boolean, version: string, customPackets?: any)
	state: States
	isServer: boolean
	socket: Socket
	uuid: string
	username: string
	session?: SessionOption
	profile?: any
	deserializer: FullPacketParser
	serializer: Serializer
	latency: number
	customPackets: any
	protocolVersion: number
	version: string
	write(name: string, params: any): void
	writeRaw(buffer: any): void
	compressionThreshold: string
	ended: boolean
	connect(port: number, host: string): void
	setSocket(socket: Socket): void
	end(reason?: string): void
	registerChannel(name: string, typeDefinition: any, custom?: boolean): void
	unregisterChannel(name: string): void
	writeChannel(channel: any, params: any): void
	signMessage(message: string, timestamp: BigInt, salt?: number): Buffer
	verifyMessage(publicKey: Buffer | KeyObject, packet: object): boolean
	on(event: 'error', listener: (error: Error) => PromiseLike): this
	on(event: 'packet', handler: (data: any, packetMeta: PacketMeta, buffer: Buffer, fullBuffer: Buffer) => PromiseLike): this
	on(event: 'raw', handler: (buffer: Buffer, packetMeta: PacketMeta) => PromiseLike): this
	on(event: 'session', handler: (session: SessionObject) => PromiseLike): this
	on(event: 'state', handler: (newState: States, oldState: States) => PromiseLike): this
	on(event: 'end', handler: (reason: string) => PromiseLike): this
	on(event: 'connect', handler: () => PromiseLike): this
	on(event: string, handler: (data: any, packetMeta: PacketMeta) => PromiseLike): this
	on(event: `raw.${string}`, handler: (buffer: Buffer, packetMeta: PacketMeta) => PromiseLike): this
	once(event: 'error', listener: (error: Error) => PromiseLike): this
	once(event: 'packet', handler: (data: any, packetMeta: PacketMeta, buffer: Buffer, fullBuffer: Buffer) => PromiseLike): this
	once(event: 'raw', handler: (buffer: Buffer, packetMeta: PacketMeta) => PromiseLike): this
	once(event: 'sessionce', handler: (sessionce: any) => PromiseLike): this
	once(event: 'state', handler: (newState: States, oldState: States) => PromiseLike): this
	once(event: 'end', handler: (reasonce: string) => PromiseLike): this
	once(event: 'concenect', handler: () => PromiseLike): this
	once(event: string, handler: (data: any, packetMeta: PacketMeta) => PromiseLike): this
	once(event: `raw.${string}`, handler: (buffer: Buffer, packetMeta: PacketMeta) => PromiseLike): this
}
```
